# Tim's week 1 assignment

This is the repository that I use to manage assignments for week 1 in
"Intro to managing assignments".

> Note: This repository is public but the tools assume that normally you'd keep
> this private.

> Note: This repository assume you are using GitHub classroom.


## Using this as an instructor

1. Install `pip install https://github.com/betatim/grading-workflow-experiments/archive/distributing-work.zip`
2. Clone this repository to your local machine
3. Create the student and autograder versions of the homework: `nbauthor master/01-lecture.ipynb`
4. Create the GitHub classroom template: `nbdistribute /tmp/week1-template`
5. Create a new repository on GitHub
6. Push the contents of `/tmp/week1-template` to the newly created assignment
7. Create a new assignment on GitHub Classroom using the repository you created
   in step 5 as source repository
8. Add the name of the GitHub organisation and the name of the assignment under
   the `assignment.organisation` and `assignment.name` keys in `config.yml`:
   ```
   assignment:
     - organisation: blahahaha
     - name: week1
   ```
9. Pretend to be a student and accept an assignment
10. run `nbgrade` which should fetch the work of the students and 'grade' it.


## Using this as a student

1. You should receive a link from the instructor, once you click that link you
   will have your own repository for this homework.
2. There will be setup instructions for you to follow in the `README.md` of the
   assignment's repository.


## Trying it out
