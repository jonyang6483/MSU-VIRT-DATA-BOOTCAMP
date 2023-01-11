
# README.md Guide
Having a nice README.md file is important for several reasons.  
1.  The README is the first content a visitor will see.  Descriptions and purposes of the repository should be simple enough that anyone can understand it's purpose.  This needs to be brief.  Often people write very long introductions but instead, provide a summary and put additional details further down in the readme.  
2.  A readme with a nice introduction and maybe an image will standout as being very professional and indicates that you have good communication and documentation skills.  
3.  Your readme also acts as a checkpoint - what other skills would you like to showcase.  This can influence your next personal project choice.  

Here is a template that I like.  I think the initial parts are nice but it is probably too detailed for our homework activities - [Link](https://github.com/sfbrigade/data-science-wg/blob/master/dswg_project_resources/Project-README-template.md).  

The below example is something more appropriate for a large project.  The goal is to make the readme an aid that helps others to:
* Quickly understand your repo's purpose - so be brief.
* Have just enough information to run the project
* Know what technologies are being used 

I suggest having a `title`, `description`, `technologies`, and any `additional analysis` for the homeworks.  For projects, you might want to add sections about `contributors`, `data source`, `installation`, and `important documents`.



<br>
<br>

  
<font color=green>**Here is a sample template:**</font>  
***  
<br>

# Homework or Project Name
### Subtitle if needed  
<br>

A description that is only a couple sentences long - a short paragraph.  Analysis of four drug compounds effects on tumor size by using pandas dataframes and the matplotlib graphing library.  Results showed that Captamulin had a significant and greater impact on tumor size after 7 weeks relative to a control and competitor brands.  
<br>  

## Methods Used  
Central Tendencies, Boxplots, T-tests  
<br>

## Technologies
Python, Matplotlib, PostgreSQL  
<br>

## Contributors 

Include this section if this was done as a group project; otherwise, omit this section.  
<br>      

## Data Source

Include original source if it is a real dataset or remove origin comment and just include local repo location:  "Data found in `images/data.csv`".  
<br>
## Installation
Code was tested using Python 3.8.  The environment also needs pandas and matplotlib. The environment was setup as follows:

```bash
conda create -n envpy38 python=3.8 anaconda
source activate envpy38
jupyter notebook
```
If environment does not include pandas or matplotlib then install the following from terminal:
```bash
conda install pandas
conda install matplotlib
```  
<br>

## Additional Analysis  (or Demo-Preview)
Good location to add in a couple images and write some conclusions.  

If this is a project that is a webapp then maybe include some images of what it does as a demo-preview.  
<br>

## Featured Notebooks/Analysis/Deliverables
|Document Title    |  Purpose   | 
|---------|-----------------|
|data_preparation.py  | Data retrieval and cleaning    |
|data_analysis.py |  Analysis - plotting and statistical tests    |  
| report.md |  Findings, suggestions, and future work.

***  
<font color=green>**End of template**</font>  
<br>
<br>
## Additional Notes:
1.  You do not need to include all the sections above.  I suggest having a title, description, technologies, and any additional analysis for the homeworks.  The other parts are probably more applicable to projects.  There are not set rules for this.
1.  When doing the analysis, it is also nice to add some images of graphs.  
1.  If you want to make it even more visually pleasing then you can use a website like [Canva](https://www.canva.com/web-banners/templates/) to make banners for the top of your readme.  There are some free options.  
    * Here is an example of a Canva web banner.  It took about 2 minutes to make this:  
![Header Image](images/readme_images/banner-(Minimalist Marble).png)  

1.  The syntax that we are using is called 'Markdown'.  There can be some syntax differences between web services that use it, but in general, it is fairly similar.  Below are some guides that will help you.   
<br>


## Resources  
***
[README.md Template](https://www.makeareadme.com/)   

[GitHub Markdown Syntax Guide](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

[GitLab Markdown Syntax Guide](https://about.gitlab.com/handbook/markdown-guide/)

[Jupyter Notebook Markdown Syntax Guide](https://ingeh.medium.com/markdown-for-jupyter-notebooks-cheatsheet-386c05aeebed)

[Ornamental Banners](https://www.canva.com/web-banners/templates/)