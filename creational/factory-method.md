# Objetivo
* Definir uma interface para criar objetos, mas deixar que a subclasse decida qual classe instanciar

# Exemplo
```php
interface Interviewer
{
    public function askQuestions();
}

abstract class Hirer
{
    public static function makeInterviewer();

    public function interview()
    {
        $interviewer = $this->makeInterviewer();
        $interviewer->askQuestions();
    }
}

class DeveloperManager extends Hirer implements Interviewer
{
    protected function askQuestions()
    {
        echo "I'm going to ask about IT stuffs";
    }
}

class DesignerManager extends Hirer implements Interviewer
{
    protected function askQuestions()
    {
        echo "I'm going to ask about colors and shapes";
    }
}
```
