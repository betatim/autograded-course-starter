# Tim's awesome course

> Note: This is an example repository.

This repository is used to manage assignments for the course
"Intro to managing courses with git stuffs".

> Note: While this repository is public, the tools assume that normally you'd
> keep this private.

> Note: This repository assumes you are using GitHub classroom.


## Concepts

As an instructor you will use this repository to manage the course material.
In the `master/` subdirectory you will keep assignments and material for the
course. It is the "master" copy of the course. Everything else will be generated
from it.

Students will have their own, private repositories for the duration of the
course. They will receive updates from the instructor as new material is
released in the form of a PR to their repository.

All configuration happens in `config.yml`.


## Terminology

**template repository**: the repository used by GitHub classroom to initialise
a student's repository when they click 'accept assignment'

**GitHub**: well known code sharing platform, abbreviated as GH


## Using this example repository (as an instructor)


### Setup steps
1. Install `pip install https://github.com/earthlab/grading-workflow-experiments/archive/master.zip`
2. Clone this repository to your local machine.
3. Make sure you are in the top directory of this repository.
4. Inspect `config.yml` and adjust it. Make sure to add your GH username
   to the list of students so you can experience the student's perspective.
5. run `nbinit` to get a GH access token, this lets the tools perform
   actions on your behalf on github.com without asking you for your
   password every time.
6. [Create a new GH organisation](https://github.com/organizations/new)
   matching the name you used for `organisation` in `config.yml`.
7. [Install the notebook bot](https://github.com/settings/apps/notebookbot/installations)
   for the organisation you just created. Make sure to enable it for
   "all repositories" in the organisation.
8. Go to https://classroom.github.com/classrooms/new and create a new classroom
   for the organisation you just created.


### One time preparation to launch a course

> Note: the dates used here fit with the defaults configured in `config.yml`
> if you changed the configuration you probably need to pick new dates here

You want to take these steps at the start of the course. As part of this
you will setup the GH classroom and template repository.
1. Create the template student repository with: `nbauthor --date 2018-01-01`.
   By using a date before the first assignment we get an essentially empty
   template repository.
2. Create the GitHub classroom template repository: `nbdistribute --template`.
3. Create your GitHub classroom assignment.
   Make sure to set "Your assignment repository prefix" to the `courseName` you
   set in `config.yml` earlier.
   For the "Add your starter code from GitHub (optional)" field use the
   template repo from the previous steps as the template repo for the
   assignment. (What GH classroom calls an assignment is a course for us.)


### Pretending to be a student

We now switch to pretending to be a student to setup one student repository
for the course.

1. Pretend to be a student and accept the "assignment" created in GH classroom.
2. Visit your "student" repository and follow the instructions in the README.
   Every student will have to do this.

Because there is nothing interesting in the repository yet there is not much
we can do. Let's release the first assignment and then come back to the
repository.


### Releasing new material to students

Back at the top of this repository.

1. Run `nbauthor --date 2018-10-11` to release the next assignment.
2. Check the `student/` repository, there should be a new subdirectory in it.
3. Run `nbdistribute` to create Pull Requests with the new material to each of
   the student's repositories. (If you listed a student who hasn't yet accepted
   the assignment there will be an exception raised, this is being fixed.)
4. Check the student repository, there should be a PR with the new material
   asking the student to merge it.
5. Go ahead and merge the PR!


### Notebook feedback

Visit the GH of your student repository. In the web interface make an edit
to the README. A little while after you commit the edit to the master branch
there should be a new issue on your repository that links to a preview of
your notebooks that have been run in the way that the auto-grader will execute
them.
