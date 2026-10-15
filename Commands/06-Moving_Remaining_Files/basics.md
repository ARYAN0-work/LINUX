# REV =>

ls -l

![alt text](image.png)

> in this video he is gonna show how he is gonna move those files around which he made earlier

cat test2.txt
learnlinux.tv

# now i am gonna copy files

cp test2.txt newfile.txt
ls -l 
![alt text](image-1.png)

> now

cat newfile.txt
learnlinux.tv
cat test2.txt
learnlinux.tv

# now this commman tells us that the file is diffrent or not 

diff newfile.txt test2.txt
> no output 
![alt text](image-2.png)

> now how should i get rid of a file
rm newfile.txt
ls -l

![alt text](image-3.png)

rm test2.txt
clear
ls -l

#### NOTE:-

rm -r directory

![alt text](image-4.png)

**NOTE** BE careful if you use rm command its gone no comeback :- theres no recycle bin or anything 

# BUT NOW HOW I CAN MOVE ONE FILE FROM ONE PLACE TO ANOTHER

![alt text](image-5.png)

i am gonna move test3 and test4 and testfile to somewhere else

- mkdir notes

now i am gonna move them here 

mv test3.txt notes
![alt text](image-6.png)

ls -l notes
![alt text](image-7.png)

mv *.txt notes [anything-that-comes-with-star]

![alt text](image-8.png)

# Something interesting

![alt text](image-9.png)

~/notes => ~: subdirectory 

mv testfile.txt .. => moving those testfiles to subdirectory

ls -l ..

![alt text](image-10.png)

mv ../testfile.txt . [move-testfile-to-cureent-directory]

![alt text](image-11.png)

(ls . == ls -l)

# how do we rename the file
> use mv [again]

mv test3.tzt abc.txt
![alt text](image-12.png)

> but if we do this 
![alt text](image-13.png)

=> uske me isliye aisa aaya bcz overwrite system hai humare mai direct ho jayega

![alt text](image-14.png)