# Lab 4: UML, GitHub Issues


In this lab, you will gain hands-on experience creating UML class diagrams from existing Java code using graphical diagramming tools such as **draw.io**, as well as generating diagrams programmatically with **Mermaid** syntax. This lab assignment will strengthen your ability to visually communicate object-oriented designs, and enhance your project management skills by utilizing GitHub issues, including creating, organizing, and writing clear, actionable issues to manage development tasks efficiently.

## Learning Objectives

- Translate code into standardized UML class diagrams
- Identify and represent inheritance relationships
- Correctly depict abstract classes, methods, and fields
- Understand visibility modifiers and their UML representation
- Use both visual UML tools (draw.io) and code-based UML (Mermaid)
- Practice using GitHub Classroom, Projects, and Issues

## The Code

The code provided below represents a simple Java application that models an animal hierarchy. You will be creating UML class diagrams based on this code.

### Abstract Animal Class
```java
public abstract class Animal {
    private String name;

    public Animal(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public abstract String makeSound();
}
```

### Dog Class
```java
public class Dog extends Animal {
    private String breed;
    
    public Dog(String name, String breed) {
        super(name);
        this.breed = breed;
    }
    
    public String getBreed() {
        return breed;
    }
    
    @Override
    public String makeSound() {
        return "Woof!";
    }
    
    public void fetch() {
        System.out.println(getName() + " is fetching!");
    }
}
```

### Cat Class
```java
public class Cat extends Animal {
    private int lives;
    
    public Cat(String name) {
        super(name);
        this.lives = 9;
    }
    
    public int getLives() {
        return lives;
    }
    
    public void loseLive() {
        if (lives > 0) {
            lives--;
        }
    }
    
    @Override
    public String makeSound() {
        return "Meow!";
    }
}
```

### Bird Class
```java
public class Bird extends Animal {
    private boolean canFly;
    
    public Bird(String name, boolean canFly) {
        super(name);
        this.canFly = canFly;
    }
    
    public boolean getCanFly() {
        return canFly;
    }
    
    @Override
    public String makeSound() {
        return "Tweet!";
    }
    
    public void fly() {
        if (canFly) {
            System.out.println(getName() + " is flying high!");
        } else {
            System.out.println(getName() + " cannot fly!");
        }
    }
}
```


## Tasks

### Task 1: Accept GitHub Classroom Assignment

Accept the the following GitHub Classroom assignment invitation, this will create a personal repository in the UC3093C organization.  You will be using this repository to manage your project and submit your work.

[https://classroom.github.com/a/w13UuPS-](https://classroom.github.com/a/w13UuPS-)

### Task 3: Create Issues

Create two GitHub issues in your repository to represent the tasks you will be completing in this lab. The titles for the tasks are:

1) "Create UML class diagram using draw.io"
2) "Create UML class diagram using Mermaid"

When creating the issue you must:

- Use the issue template (in markdown syntax) provided below.  Make sure to make minior adjustments to the template to fit your specific task.  
- Assign the issues to yourself.
- Add "documentation" as a label.
- Add "UML" as a label, but you will need to create this label first. Use "UML" as the name and "UML diagrams" for the description.
- Specify "Task" as the issue type.

![](/images/github_issue.png)


**Issue Template**

Use the issue template provided below to create the issue description.

When creating your GitHub issues, use the following markdown template for your issue description:

```{admonition} Issue Template (click here!)
:class: tip, dropdown

    ```markdown
    ## Description
    Create a UML class diagram that accurately represents the Animal class hierarchy using [draw.io OR Mermaid].

    ## Requirements
    - Represent all four classes: Animal, Dog, Cat, and Bird
    - Show all attributes with proper visibility notation
    - Show all methods with proper visibility notation
    - Include return types and parameters for methods
    - Properly indicate the abstract class and abstract method
    - Show all inheritance relationships
    - Follow standard UML notation

    ## Acceptance Criteria
    - [ ] All classes are correctly represented
    - [ ] All attributes are shown with proper visibility
    - [ ] All methods are shown with proper visibility
    - [ ] Abstract class and method are properly indicated
    - [ ] Inheritance relationships are correctly shown
    - [ ] Diagram is saved as an image file.
    - [ ] Diagram is committed to the repository
    ```
```


### Task 4: Visual UML Class Diagram with draw.io

1. Move this issue to "In Progress" in your Kanban board
2. Create a complete UML class diagram using draw.io that represents all four classes in the code
3. Export the diagram as a PNG or JPEG file
4. Commit this file to your repository with the message "Completed UML class diagram in draw.io - fixes #X" (where X is your issue number)
5. Move the issue to "Done" in your Kanban board

### Task 5: Code-based UML Class Diagram with Mermaid

1. Move this issue to "In Progress" in your Kanban board
2. Create a markdown file in your repository named `UML-class-diagram.md`
3. Use Mermaid syntax to create the class diagram in this file
4. Commit the file with the message "Completed UML class diagram in Mermaid - fixes #Y" (where Y is your issue number)
5. Move the issue to "Done" in your Kanban board


## Mermaid

[Mermaid](https://mermaid.js.org) is a JavaScript-based diagramming and charting tool that uses Markdown-inspired syntax. It allows you to create diagrams and visualizations directly in your markdown files. 

Mermaid supports various types of diagrams, including flowcharts, sequence diagrams, and class diagrams. In this lab, you will use Mermaid to create a class diagram that represents the same classes and relationships as in the draw.io diagram.  Please see the [Mermaid class diagram documentation](https://mermaid.js.org/syntax/classDiagram.html) for more details on syntax and features.

GitHub supports rendering Mermaid diagrams directly in markdown files, so you can include your class diagram in the `UML-class-diagram.md` file you create.

## Grading

### Deliverables

1. A GitHub repository containing:
   - PNG/JPEG file of your draw.io UML class diagram
   - A markdown file named `UML-diagram.md` with Mermaid code for the class diagram

2. A completed GitHub Project board showing your workflow progression (both tasks should be in the "Done" column)

3. GitHub Issues that are properly closed by your commits


### Following proper UML notation guidelines

1. **Class Representation**:
   - Regular classes: Rectangle with solid lines
   - Abstract classes: Rectangle with solid lines, class name in *italics*

2. **Visibility Modifiers**:
   - Public: +
   - Private: -
   - Protected: #
   - Package: ~ (no modifier)

3. **Methods**:
   - Format: visibility name(parameters): returnType
   - Abstract methods should be in *italics*

4. **Attributes**:
   - Format: visibility name: type

5. **Inheritance**:
   - Shown with an arrow pointing from the subclass to the superclass
   - Use a solid line with a hollow triangular arrowhead


### Grading Rubric

- Correct representation of classes and relationships in class diagram, proper use of UML notation for visibility, abstract classes, and methods (50%)
  - Correct implementation using draw.io diagram (25%)
  - Correct implementation using Mermaid diagram (25%)
- Proper use of GitHub Classroom, Projects, and Issues with correct issue template (50%)
  - Correctly created and managed GitHub Project (20%)
  - Correctly created and managed GitHub Issues (20%)
  - Proper commit messages and issue linking (10%)