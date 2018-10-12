# Tim's week 1 assignment

This is the repository that I use to manage assignments for week 1 in
"Intro to managing assignments".

> Note: This repository is public but the tools assume that normally you'd keep
> this private.

> Note: This repository assume you are using GitHub classroom.


## Using this as an instructor

1. Install `pip install https://github.com/betatim/grading-workflow-experiments/archive/distributing-work.zip`
2. Clone this repository to your local machine
3. Inspect `config.yml` and adjust it
4. Make sure you are in the top directory of this repository
5. run `nbinit` to get a GitHub access token
5. Create the template student repository with: `nbauthor --date 2018-01-01`
   By using a date before the first assignment we get an essentially emtpy
   template repository.
6. Create the GitHub classroom template: `nbdistribute --template`
5. Create your GitHub classroom assignment and use the template repo as the
   template repo (What GH classroom calls an assignment is a course for us)
5. Pretend to be a student and accept the "assignment".
5. Make sure your GitHub username is listed in `config.yml` as a student
5. Run `nbgrade`. This will collect each student's repository and 'grade' it
   (currently grading is just a dummy step)
5. Run `nbauthor --date 2018-10-11` to release the next assignment.
5. Inspect the student sub-directory, it should contain a new assignment
5. run `nbdistribute` to create Pull Requests with the new material to each of
   the student's repositories.
5. Check the student repository, there should be a PR with the new material
   asking the student to merge it.

## Using this as a student

1. You should receive a link from the instructor, once you click that link you
   will have your own repository for this homework.
2. There will be setup instructions for you to follow in the `README.md` of the
   assignment's repository.


## Trying it out
