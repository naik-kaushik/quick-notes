
# Scenario 

1. We have below shown tables
2. we want to write a trigger such that the `total_questions` field in `quiz` is updated automatically on inserting a question that `belongs_to` given `quiz`.

![[Pasted image 20240822195713.png]]

## Procedure


```pgsql
CREATE OR REPLACE FUNCTION increment_total_questions() 
RETURNS TRIGGER AS $$
BEGIN
    UPDATE quiz q
    set total_questions = total_questions + 1
    where q.quiz_id = NEW.belongs_to;
    RETURN NEW;
END;
$$ LANGUAGE plpgsql;
```


## Trigger

```pgsql
CREATE TRIGGER trigger_increment_total_questions
AFTER INSERT ON question
FOR EACH ROW
EXECUTE PROCEDURE increment_total_questions();
```


