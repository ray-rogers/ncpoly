Superficial instructions
raymond.rogers72@gmail.com
or
fricas-devel@googlegroups.com
might reach me.

To initialize please dump the relevant files
into a clean directory. 
run 
fricas 
from a console in that directory

)read test_init.input
You should only have to add tests to tests.input
After adding or modifying tests
)read tests.input
without reinitializing.
Actually test_init.input can be merger with nc_ini03-a.input
test_init.input only has 2 items
1) A equality test factCheck
   to see if the found factors multiply to the input.
2) A record of the test done.  I have found that keeping
   a detailed record/log where all of the important intermediate 
   results can be found in an organized list oriented manner is
   beneficial for debugging and maintenence.

Adding tests should consist of lines like
testname : NCP := equation
testrecord = buildrecord(testname :: NCP)
You should get a last line of pass/fail/nil indicating the result

Actual factors accessed by
testrecord.polFactors

The test "record" is presently defined in test_init.input 
To add record field just follow the model.
Three entries are needed to add a field.
1) NCPrecord : Record ...  just like the ones already there
2) a new "nil" in the list at the NCPrecord end.
3) a entery in buildrecord that will assign a value to the
   new field.  This build only operates from the input 
   NCP/equation.
and the intermediate record field names can be listed by 
NCPrecord
With names and results
testrecord
Just look at tests.input to see how.  Only two lines are needed.
Plus a line
testrecord.NCpass
to see if it worked.
Different test sequences can be run by alternate files and
)read alternate file name


