---
tags:
  - Daily-Note
  - Year-<%tp.file.creation_date("YYYY")%>
  - Q<%tp.file.creation_date("Q")%>
  - <%tp.file.creation_date("MM-MMMM")%>
  - Week-<%tp.file.creation_date("WW")%>
---
>[!abstract] Daily Note Guidelines  
_This note is the heart of your daily productivity and reflection. It’s where you manage tasks, track habits, and align your day-to-day actions with your larger goals and vision. By focusing on what matters most, capturing thoughts as they arise, and maintaining consistency, the daily note becomes your command center for creating a life of intentional progress and balance. Use it to stay organized, inspired, and reflective as you navigate each day._


---
<%*

const periodNotesBasePath = "";
const journalBasePath = ""
const quickCaputrePath = ""

const today = new Date();

const dayOfWeek = today.getDay(); 
const dayOfMonth = today.getDate();
const month = today.getMonth(); 
const weekOfYear = Math.ceil((today.getDate() + new Date(today.getFullYear(), today.getMonth(), 1).getDay()) / 7);

const creationYear = tp.file.creation_date("YYYY");
const creationQuarter = tp.file.creation_date("Q");
const creationMonth = tp.file.creation_date("MM-MMMM");
const creationWeek = tp.file.creation_date("WW");
const creationDay = tp.file.creation_date("YYYY-MM-DD-dddd");

const isFirstWeekOfYear = weekOfYear === 1 && month === 0;
let weekNumber = tp.file.creation_date("WW"); 
console.log(dayOfWeek)
if (dayOfWeek === 0) {

weekNumber = String(parseInt(weekNumber) + 1).padStart(2, '0'); 
}

const isFirstWeekOfQuarter = 
    (month % 3 === 0 && weekOfYear === 1) || 
    (month % 3 === 0 && today.getDate() <= 7 && today.getDay() < 7);
    
const isFirstWeekOfMonth = dayOfMonth <= 7;

const isFirstThreeDaysOfWeek = dayOfWeek === 0 || dayOfWeek === 1 || dayOfWeek === 2

const weeklyFilePath = `${periodNotesBasePath}/Weekly Notes/${creationYear}/Q${creationQuarter}/${creationMonth}/${weekNumber}`;

const monthlyFilePath = `${periodNotesBasePath}//Monthly Notes/${creationYear}/Q${creationQuarter}/${creationMonth}`;

const quarterlyFilePath = `${periodNotesBasePath}//Quarterly Notes/${creationYear}/Q${creationQuarter};

const yearlyFilePath = `${periodNotesBasePath}//Yearly Notes/${creationYear}`;

const journalFilePath = `${journalBasePath}/${creationYear}/Q${creationQuarter}/${creationMonth}/${creationWeek}/${creationDay} - Journal`;

if (isFirstWeekOfYear) {

    const currentFile = app.vault.getAbstractFileByPath(yearlyFilePath + ".md");
    if (!currentFile) {
        -%>
---
# Dream Big for the Year Ahead

>[!hint] Happy new year!
*It's a new year! Dream boldly and set your direction—your yearly vision is the key to achieving your aspirations!*


![[<% yearlyFilePath %>]]


---



<%* 
    }
}

if (isFirstWeekOfQuarter) { 

    const currentFile = app.vault.getAbstractFileByPath(quarterlyFilePath+ ".md");
    if (!currentFile) {
        -%>
---
# Set Ambitions for the Quarter

>[!tip] A fresh quarter is here!
*Think big and break your ambitions into achievable steps to stay on track with your vision.*


![[<% quarterlyFilePath %>]]


---



<%* 
    }
}

if (isFirstWeekOfMonth) { 

    const currentFile = app.vault.getAbstractFileByPath(monthlyFilePath + ".md");
    if (!currentFile) {
        -%>
---
# Plan for the Month Ahead

>[!tip] A new month brings new opportunities
*Organize your thoughts and priorities to stay focused and productive.*


![[<% monthlyFilePath %>]]


---



<%* 
    }
}

if (isFirstThreeDaysOfWeek) {

    const currentFile = app.vault.getAbstractFileByPath(weeklyFilePath + ".md");
    if (!currentFile) {
        -%>
---
# Kick Off Your Week

>[!tip] It's a fresh start to the week! 
*Take a moment to reflect on your goals and plans to set the tone for success.*


![[<% weeklyFilePath %>]]


--- 



<%* 
    }
}

const shouldDisplayAmbition = Math.random() < 0.1;

    if (shouldDisplayAmbition) {


const shouldDisplayYearlyNote = Math.random() < 0.1;
const shouldDisplayMonthlyNote = Math.random() < 0.3;
const shouldDisplayQuarterlyGoals = Math.random() < 0.4;

    if (shouldDisplayMonthlyNote) {
        -%>
---
# Stay on Track with Your Monthly Plan

>[!tip] Don’t let the month slip by! 
Revisit your priorities and ensure your goals are aligned to make steady progress.


![[<% monthlyFilePath %>#Planning]]


---



<%* 
    }  if (shouldDisplayQuarterlyGoals) {

-%>
--- 
# Focus on Your Quarterly Goals

>[!tip] Take this opportunity to refocus and realign! 
Break down your big vision into actionable steps and make meaningful progress this quarter.


![[<% quarterlyFilePath %>#Goals]]


--- 



<%* 



    }  if (shouldDisplayYearlyNote) {

-%>
--- 
# Dont Forget your Yearly Vision!

>[!tip] Stay inspired and keep your yearly vision in mind!
It's your guiding light for achieving your dreams and staying on track throughout the year.


![[<% yearlyFilePath %>#Vision]]


--- 



<%* 
    
}

}
-%>
# Quick Capture 

![[<%quickCaputrePath %>/quick-capture]]


---
# Overview
## Focus 

>[!tip] Set your intension for the day
Sets the primary focus for the day and give the day some purpose and direction



## Agenda 

>[!tip]  Plan your agenda for the day
What do you have on your plate for today? write out the things you need to get done, upcoming meetings, or activities that needs to get done



---
# Today's Tasks
#### Due Today
```tasks
not done

due on <% tp.file.creation_date("YYYY-MM-DD") %>

```


#### New Today
- [ ]



---
# Daily Tracking
## Journal Entry 

![[<% journalFilePath %>#Daily Tracking]]



---
# Periodic Notes
## Weekly Planning

![[<% weeklyFilePath %>#Planning]]


## Monthly Planning

![[<% monthlyFilePath %>#Planning]]


## Quarterly Goals

![[<% quarterlyFilePath %>#Goals]]


## Yearly Vision

![[<% yearlyFilePath %>#Vision]]



---
# Tasks
## Over Due
```tasks
path does not include Template
not done

due before <% tp.file.creation_date("YYYY-MM-DD") %>

```
## No Due Date
```tasks
path does not include Template
not done

no due date

```


---
# Tracker 
## Tasks Done Today

```tasks

done on <% tp.file.creation_date("YYYY-MM-DD") %>

```
