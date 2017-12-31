# gb -- a Bash and `recutils` gradebook

Last updated: Dec. 31, 2017

## Background

This program grew out of three converging issues: an interest in learning
and using the text-based, human-editable `recutils` format for storing
information; a frustration with the limited capabilities of the gradebook
feature of Blackboard; and a desire to have fine-grained control, preferably
from the command line, over both individual student records as well as
aggregate class statistics.

`gb` is intended as a helper program, to augment manual editing of the
text-based gradebook in `recutils` format, though over time the program has
been made capable of handling most common gradebook tasks.

## Operating philosophy

`gb` is built around a gradebook in which every assignment is an "item" that
is found within a "category." Each "category" is given some specified
percent of the overall course grade.  The category's share of the grade is
distributed equally across all the individual items in the category.

Let's say a student's grade is made up of two exams, each worth 25% of the
final grade; a series of five quizzes, collectively worth 30% of the course
grade, and an essay, worth 20% of the course grade.  The grading schema might look like so:

- category "exams", worth 50% of final grade; items "midterm" and "final"
- category "quizzes", worth 30% of final grade; items "quiz1" through "quiz5"
- category "essay", worth 20% of final grade; one item "essay"

A category can be set to automatically drop the lowest grade -- for example,
six quizzes might be taken, but the lowest one dropped.  An item may also
count as a "bonus" within a category.

The category/item structure means that impromptu or unexpected
assignments, such as a pop quiz or a graded discussion, can be added to a
category without impacting the balance of the grading for the rest of the
course.  If, for example, one category was "participation" grades, an
instructor could add assignments, skip them, or add bonus items without
impacting the overall proportion of the course grade allocated to the
various categories.

## Installation

Download and locate somewhere in your $PATH.  Ensure dependencies are met
(`gb` will check for them, but Bash is also needed).

## Usage

`gb help` (or simply `gb`) provides a synopsis of available commands.

## Caveats

Developed on a Debian Linux system. Suggestions to enhance portability to
other Unix-like systems would be welcomed, though Bash will continue to be
required because of `readrec`.

