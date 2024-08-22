"_The main difference? Bloc is event driven while cubit works with functions._"
## BlocProvider

- BlocProvider is common to both Cubit and BLoC.
- In order to manage [app states](https://docs.flutter.dev/data-and-backend/state-mgmt/ephemeral-vs-app), we need to wrap the home widget in BlocProvider.
- That is put BlocProvider at the top of the widget tree.
- Hence BlocProvider is called as *dependency injection* widget.
- `BlocProvider.value()` is used to pass existing instance of a cubit.

```dart
home: BlocProvider(  
  create :(_) => CounterCubit(),  
  child: const MyHomePage(title: 'Counter Stream'),  
),
```

## Cubit 

- Cubit = smaller implementation of BLoC.
- Cubit class includes initialization of the state and the management of state can be done by emit() method.

```dart
class CounterCubit extends Cubit<int>{  
  CounterCubit() : super(0);  
  
  void increment() => emit(state+1);  
  
  void decrement() => emit(state-1);  
}
```

- To send events,

```dart
onPressed: () => {context.read<CounterCubit>().decrement()}
```


## BLoC

- Business Logic Components.
- Firstly create an abstract class for concerned Event.
- Then create subclasses related to state actions. These subclasses should inherit abstract class.
- State management can be carried out using `on<StateAction>((event,emit){})`

```dart
import 'package:flutter_bloc/flutter_bloc.dart';  
  
abstract class CounterEvent {}  
  
class Increment extends CounterEvent{}  
  
class Decrement extends CounterEvent{}  
  
  
class CounterBloc extends Bloc<CounterEvent,int>{  
  CounterBloc() : super(0){  
  
    on<Increment>((event,emit)=>  
      emit(state+1)  
    );  
  
    on<Decrement>((event,emit)=>  
      emit(state-1)  
    );  
  
  }  
}
```

- To send events,

```dart
onPressed: () => {context.read<CounterBloc>().add(Decrement())},
```


## BlocListener : why do we need it?

1. We use BlocBuilder to make sure that the UI rebuilds whenever there is change in state. But for the elements like `snackbar` or `dialogBox`, we cannot show them in builder because the builder func inside `BlocBuilder` can get called multiple times.
2. To tackle this problem, we have BlocListener which has a listener parameter which makes sure anything insider listener gets executed only once whenever there is desired change in state.

## BlocConsumer the better solution

1. In order to combine usefulness of both builder and listener we use consumer. It has both params builder and listener to make things easy.

## Different Scenarios

1. When a Screen is using the bloc in its context, there is no problem in accessing the bloc state and data but as soon as a new screen/dialog is pushed, the existing context breaks and new context is created. In order to pass bloc to this new screen's new context, we don't instantiate a new bloc object. Rather we pass it using `BlocProvider.value()` .
2. Different cubits can communicate with each other using `cubit.listen()` or just use `BlocListener` .
3. 