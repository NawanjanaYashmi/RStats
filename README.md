# lab 3

#import file
#FOR READ txt file we use read.table command

```bash
data<-read.csv("DATA 3.csv",header = TRUE)
data
```

#get data into edetor mode 

```bash
fix(data)
```

#rename the coloumns

```bash
names(data)<-c("Age","Gender","Accomodation")
```
#rename cetegorical data

```bash
data$Gender<-factor(data$Gender,c(1,2),c("Male","Female"))
data$Accomodation<-factor(data$Accomodation,c(1,2,3),c("Home","Boarded","Lodged"))
fix(data)


attach(data)
```

#Q2
#frequancy table

```bash
gender.freq<-table(Gender)
acc.freq<-table(Accomodation)
gender.freq
acc.freq
```

#pie chart

```bash
pie(gender.freq,"pie chart for gender")
pie(acc.freq,"pie chart for accomodation")
```

#barplot or barchart

```bash
barplot(gender.freq,main = "Bar plot for gender", ylab = "Frequancy")
abline(h=0)
barplot(acc.freq,main = "Bar Plot for Accomodation", ylab = "Frequancy")
abline(h=0)
```

#box plot

```bash
boxplot(Age,main="Boxplot for Age", ylab="Age",outpch=8)
```

#Q3
#Two way frequency table

```bash
gender_acc.freq<-table(Gender,Accomodation)
gender_acc.freq
```

#stack bar chart or plot

```bash
barplot(gender_acc.freq,main = "gendaer and accomodation",legend=rownames(gender_acc.freq))
abline(h=0)
```


#clustered barchart

```bash
barplot(gender_acc.freq,beside = TRUE,main = "gendaer and accomodation",legend=rownames(gender_acc.freq))
```

#Q4
#side by side boxplot

```bash
boxplot(Age~Gender,main="Boxplot for age by gender ",xlab = "Gender",ylab = "Age")
boxplot(Age~Accomodation,main="moxplot for age by accomodation",xlab = "accomodation",ylab = "Age",horizontal = TRUE)
```

#Q5

```bash
xtabs(Age~Gender+Accomodation)/gender_acc.freq
```

---------------------------------------------------------------------------------------------------------------

# Lab 4


#inport file

```bash
data<-read.table("DATA 4.txt", header = TRUE, sep = "")
fix(data)
data
```

#naming coloumns

```bash
names(data)<-c("Team","Attendance","Salary","Years")
```

#accessing veriables or coloumns derectly without calling whole dataset

```bash
attach(data)
```

#Q2
#boxplot

```bash
boxplot(Attendance,main="boxplot for Attendence",outline = TRUE,xlab="attendance",horizontal = TRUE)
boxplot(Salary,main="boxplot for salary",outline = TRUE,xlab="salary",horizontal = TRUE)
boxplot(Years,main="boxplot for years",outline = TRUE,xlab="years",horizontal = TRUE)
```

#histrogram

```bash
hist(Attendance,main = "Histrogram for attendance",ylab = "Frequancy")
abline(h=0)
hist(Salary,main = "Histrogram for Salary",ylab = "Frequancy")
abline(h=0)
hist(Years,main = "Histrogram for years",ylab = "Frequancy")
abline(h=0)
```

#Stem Leaf

```bash
stem(Attendance)
stem(Salary)
stem(Years)
```

#mean

```bash
mean(Attendance)
mean(Salary)
mean(Years)
```

#median

```bash
median(Attendance)
median(Salary)
median(Years)
```

#standered deveation

```bash
sd(Attendance)
sd(Salary)
sd(Years)
```

#summary value

```bash
summary(Attendance)
summary(Salary)
summary(Years)
```

#Quartile

```bash
quantile(Attendance)
quantile(Attendance)[2]#first quantile
quantile(Attendance)[4]#third quantile
```

#inter quatile range(IQR)

```bash
IQR(Attendance)
IQR(Salary)
IQR(Years)
```


#Q3

```bash
get.modes<-function(y){
  counts<-table(y)
  names(counts)[counts==max(counts)]
}

get.modes(Years)
```


#Q4

```bash
get.outliers<-function(y){
  q1<-quantile(y)[2]
  q3<-quantile(y)[4]
  iqr<-q3-q1
  lb<-q1-1.5*iqr
  ub<-q3+1.5*iqr
  print(paste("upper Bound",ub))
  print(paste("lower bound",lb))
  print(paste("outliers",paste(sort(y[y<lb|y>ub]),collapse = ",")))
}
get.outliers(Years)
get.outliers(Attendance)
get.outliers(Salary)
```

---------------------------------------------------------------------------------------------------------------

#   Lab 5

Q1

```bash
data<-read.table("Data.txt", header = TRUE, sep = ",")
data
fix(data)
str(data)
names(data)<-c("company", "noOfShareholders")
attach(data)
hist(noOfShareholders,main = "shareHolders",ylab = "Frequancy")
abline(h=0)
```

#########################33

```bash
min(noOfShareholders)
max(noOfShareholders)
summary(noOfShareholders)
boxplot(noOfShareholders, horizontal = TRUE, outline = TRUE)

IQR(noOfShareholders)
```

#Q2

```bash
breaks<-seq(from = 130, to = 270, length.out = 8)
hist(noOfShareholders,breaks = breaks,main = "shareHolders",ylab = "Frequancy")
abline(h=0)
```

---------------------------------------------------------------------------------------------------------------
# Lab 2

###controll statement
#if

```bash
x<-4
x
if(x>0){
  print("positive number")
}
```

#if else

```bash
x<-7
y<--2
y
if(y>0){
  print("positive number")
}else{
  print("negetive number")
}
```

#nested if

```bash
x<-0
if(x>0){
  print("positive number")
}else if(x<0){
  print("negetive number")
}else{
  print("number is zero")
}
```


#while loop

```bash
i<-1
while(i<6){
  print(i)
  i=i+1
}
```

#for loop(print 6,7,8,9,10)

```bash
6:10
for (i in 1:10) {
  print(i)
}
```



#######controll statement
##csv file and text file 

```bash
data1<-read.csv("DATA 2.csv")
fix("data1")#to open data editor mode
data1
```
#write data in file

```bash
index<-c(1,2,3)
Name<-c("kamal", "numal", "sunil")
marks<-c(23,45,30)

dataFrame<-data.frame(index,Name,marks)
dataFrame

write.csv(dataFrame,"dataframe1.csv")
write.table(dataFrame,"dataframe2.txt")
```

####functions

```bash
function_01<-function(a,b){
  y<-a+b
  print(y)
}
```
#calling function

```bash
function_01(5,5)
```
---------------------------------------------------------------------------------------------------------------


# Lab 01

```bash
print(100:150)
```

#assingment operators
#local environment

```bash
a=5
a<-5
```

#global environment (normally used in functions)
```bash
a<<-5
```

#fundamentals data objects
#vector

```bash
w<-c(1,2,3,4,5)
w
class(w)

e<-c(10,20,0,30,50)
e
class(e)

r<-c("sundar")
r
class(r)
```

#factor(category ex= 0 or 1 it will cotogorize 0 and 1 )

```bash
gender<-c(0,1,1,1,0,0,1,0)
gender

Gender<-factor(gender,c(0,1),c("Male","Female"))
Gender
class(Gender)
class(gender)
```


#list

```bash
p<-c(1,2,30)
q<-c("green")
r<-c(21)
p
q
r
Data<-list(p,q,r)
Data
class(Data)
```

#Metrix

```bash
matrix1<-matrix(c(1,2,3,4),nrow = 2,ncol = 2,byrow = TRUE)
matrix1

matrix2<-matrix(c(1,2,3,4),nrow = 2,ncol = 2,byrow = FALSE)
matrix2
class(matrix1)
```

#data frame

```bash
height<-c(22,36,55,90)
weight<-c(56,89,22,45)

data_set<-data.frame(height,weight)
data_set
```
---------------------------------------------------------------------------------------------------------------
# Lab 03
