# Code
// SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.7.0 <0.9.0;

/**
 * @title Result
 * @dev Store,calculate & retrieve value in a variable
 * @custom:dev-run-script ./scripts/deploy_with_ethers.ts
 */
 contract Result {
     
     string rollnumber; // rollnumber for student's rollnumber
     string name; // name for student's name
     string dept; // dept for student's department
     int8 m1; // marks for subject one
     int8 m2; // marks for subject two
     int8 m3; // marks for subject three
     int8 m4; // marks for subject four 
     int8 m5; //marks for subject five 
     int8 total; // variable to store total of all subjects marks
     int8 avg; // variable to store the average of all subjects
      /**
     * @dev Store value in variable
     * @param rollno value to store roll number of the student 
     * @param nam value to store name of the student
     * @param dep value to store the department of student
     * @param one value to store marks of subject 1
     * @param two value to store marks of subject 2
     * @param three value to store marks of subject 3
     * @param four value to store marks of subject 4
     * @param five value to store marks of subject 5
     */
     function store(string memory rollno,string memory nam,string memory dep,int8 one,int8 two,int8 three, int8 four, int8 five)public{
     rollnumber = rollno;
     name = nam;
     dept = dep;
     m1 = one;
     m2 = two;
     m3 = three;
     m4 = four;
     m5 = five;

     }
     /**
     @dev add value to store total of all marks
     **/
     function add() public {
         total = m1+m2+m3+m4+m5;
     }
     /**
     @dev avg value to the average of all marks
     **/
     function average() public{
         avg=total/5;
     }
     /**
     @dev display value to display all details
     **/
     function display() public view returns (string memory,string memory,string memory,int8,int8)
     {
         return (name,rollnumber,dept,total,avg);
     }
 }
