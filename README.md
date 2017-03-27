## How to Prepare and Submit This Assignment

1. Modify the `README.md` file and [**commit**][ref-commit] changes to complete your report.
1. Ensure your changes (report in `md` file, added `rkt` file(s), and images) are committed to your forked repository.
1. [Create a **pull request**][pull-request] on the original repository to turn in the assignment.

## Csv-reading
My name: Jonathan Murphy

I wanted to play around with the CSV file library, I intend to use CSV files in the final project to read and store data.

I borrowed the following code from the racket documents

~~~~
(define make-food-csv-reader
  (make-csv-reader-maker
   '((separator-chars            #\|)
     (strip-leading-whitespace?  . #t)
     (strip-trailing-whitespace? . #t))))

(define next-row
  (make-food-csv-reader (open-input-file file)))
~~~~

This let me work my way through the csv file. I found an example csv data [here](http://www.baseball-reference.com/managers/coxbo01.shtml) and included the file "baseballdatabank-master/core/Schools.csv" that I mainly used for data.

I did 2 seperate function, the first being '(print-all)' which just printed out the raw data. All the output is in print-all.txt, excerpt here:

~~~~
(casierr,Sierra College,Rocklin,CA,USA)
(casiski,College of the Siskiyous,Weed,CA,USA)
(casjcco,San Jose City College,San Jose,CA,USA)
(casjdjc,San Joaquin Delta College,Stockton,CA,USA)
(caskyli,Skyline JC,San Bruno,CA,USA)
(casmjco,Santa Monica College,Santa Monica,CA,USA)
(casolan,Solano Community College,Fairfield,CA,USA)
(casrjco,Santa Rosa Junior College,Santa Rosa,CA,USA)
(caswjco,Southwestern College,Chula Vista,CA,USA)
(catafjc,Taft College,Taft,CA,USA)
(catawba,Catawba College,Salisbury,NC,USA)
(catholic,Catholic University of America,Washington,DC,USA)
(caventu,Ventura College,Ventura,CA,USA)
(cawhjco,West Hills College,Coalinga,CA,USA)
~~~~

The second function I made, I named statement and had it print out a number of statements. I first make a helper function named 'nth-item' that takes in the csv object and an index number and returns the correct value.

So with (nth-item '("adrianmi,Adrian College,Adrian,MI,USA") 3), you get "MI".

So I wrote:


~~~~
(define (statement)
  (next-row2)
  (define var (next-row2))

  (while (not (empty? var))
         (begin (display "The school ")
                (display (nth-item var 1))
                (display " is located in ")
                (display (nth-item var 2))
                (display ", ")
                (display (nth-item var 3))
                (display " in ")
                (display (nth-item var 4))
                (display ".\n")
                (set! var (next-row2)))))
~~~~

Write what you did!
Remember that this report must include:

* a narrative of what you did
* highlights of code that you wrote, with explanation
* output from your code demonstrating what it produced
* at least one diagram or figure showing your work

The narrative itself should be no longer than 350 words.

You need at least one image (output, diagrams). Images must be uploaded to your repository, and then displayed with markdown in this file; like this:

![Output](FP3.png?raw=true "test image")
