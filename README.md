# multiple-details
using System;<br>
namespace exersises<br>
{<br>
    class PersonalDetails<br>
    {<br>
        string name;<br>
        int age;<br>
        string gender;<br>
        public PersonalDetails(string name, int age, string gender)<br>
        {<br>
            this.name = name;<br>
            this.age = age;<br>
            this.gender = gender;<br>
        }<br>
        public virtual void display()<br>
        {<br>
            Console.WriteLine("\n Personal Details.../n");<br>
            Console.WriteLine("name          :" + name);<br>
            Console.WriteLine("age           :" + age);<br>
            Console.WriteLine("gender        :" + gender);<br>
        }<br>
    }<br>
    class CourseDetails : PersonalDetails<br>
    {<br>
        int regNo;<br>
        string course;<br>
        int semester;<br>
        public CourseDetails(string name, int age, string gender, int regNo, string course, int semester)<br>
                    : base(name, age, gender)<br>
        {<br>
           this.regNo = regNo;<br>
           this.course = course;<br>
          this.semester = semester;<br>
        }<br>
        public override void display()<br>
        {<br>
            base.display();<br>
            Console.WriteLine("Register Number       :" + regNo);<br>
            Console.WriteLine("course                :" + course);<br>
            Console.WriteLine("semester              :" + semester);<br>
        }<br>
    }<br>
    class MarksDetails : CourseDetails<br>
    { <br>      
        int[] marks = new int[5];<br>
        int total;<br>
        float average;<br>
        string grade;<br>
        int flagFail;<br>
        public MarksDetails(string name, int age, string gender, int regNo, string course, int semester, int[] marks)<br>
            : base(name, age, gender, regNo,course,semester)<br>
        {<br>
            total = 0;<br>
            for (int i = 0; i < 5; i++)<br>
            {<br>
                this.marks[i] = marks[i];<br>
                total += marks[i];<br>
                if (marks[i] < 35)<br>
                {<br>
                    flagFail = 1;<br>
                }<br>
            }  <br>
    Calculate();<br>
}<br>
        private void Calculate()<br>
        {<br>
            average = total / 5;
            if (flagFail == 1 || average < 40)<br>
                grade = "fail";<br>
            else if (average >= 70)<br>
                grade = "distinction";<br>
            else if (average >= 60)<br>
                grade = "first class";<br>
            else if (average >= 50)<br>
                grade = "second class";<br>
            else<br>
                grade = "pass class";<br>
        }<br>
        public override void display()<br>
        {<br>
                 base.display();<br>
                Console.WriteLine("\n ...MARKS DETAILS....../n");<br>
                Console.Write("marks in five subject:");<br>
                for (int i = 0; i < 5; i++)<br>
                Console.Write(marks[i] + " ");<br>
                Console.WriteLine();<br>
                Console.WriteLine("total    :" + total);<br>
                Console.WriteLine("average   :" + average);<br>
                Console.WriteLine("grade    :" + grade)<br>
            }<br>
        }<br>
        class Multilevel<br>
        {<br>
            public static void Main(string[]args)<br>
            {<br>
                MarksDetails Student1 = new MarksDetails("Abhijith", 22, "male", 20190001,"MSC", 5, new int[] { 77, 80, 98, 95, 90 });<br>
                Student1.display();<br>
            }<br>
        }<br>
    }<br>
    
    output
    ![Screenshot 2022-02-18 111155](https://user-images.githubusercontent.com/98301023/154624788-6804ac3f-f67c-44ca-b157-26937a2ead72.png)

    

  

     

    



     
