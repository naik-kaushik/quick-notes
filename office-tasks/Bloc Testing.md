## blocTest and what does it takes?

```dart
blocTest<DeleteUserCubit, UiState>(
        'SuccessState - Testing DeleteUserCubit '
        'Given the delete button is clicked '
        'Then the Loading State and SuccessState is emitted',
        build: () {
          // stubbing
          when(
            () => mockUserRepository.deleteUser(any()),
          ).thenAnswer(
            (_) async {
              return Future.value(
                Response('Response Body', 204),
              );
            },
          );
          return DeleteUserCubit(userRepository: mockUserRepository);
        },

        // act
        act: (deleteUserCubit) => {
          deleteUserCubit.deleteUser(7030442),
        },

        // assert
        expect: () => [
          isA<LoadingState>(),
          isA<SuccessState>(),
        ],
      );
```

1. Above is the code for testing `delete_user_cubit` . `blocTest<Cubit,UiState>` is used to write tests using blocTest.
2. `blocTest` mainly has three components to it : `build`  , `act`  , `expect` .
3. `build` involves stub code for the mocked components in the testing scenario.
4. `act` defines the actual actions on which the tests are being written.
5. `expect` includes assertions or the actual tests.
6. All these components : `build` , `act` , `expect` take a callback.