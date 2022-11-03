
# SAACO3
![[Pasted image 20221030210745.png]]
## Introduction
This is a personal collection of notes taken in preparation for the AWS SAA-C03 certification. 

## Ressources Used

### Courses
- [Ultimate AWS Certified Solutions Architect Associate (SAA) | Udemy](https://www.udemy.com/course/aws-certified-solutions-architect-associate-saa-c03/)

### Practice Exams
- [Practice Exams | AWS Certified Solutions Architect Associate | Udemy](https://www.udemy.com/course/practice-exams-aws-certified-solutions-architect-associate/)
- [AWS Certified Solutions Architect Associate Practice Exams - Tutorials Dojo](https://tutorialsdojo.com/courses/aws-certified-solutions-architect-associate-practice-exams/)
### Creating Notes
- [Obsidian](https://obsidian.md/)
### Website 
- [Material for MkDocs (squidfunk.github.io)](https://squidfunk.github.io/mkdocs-material/)
- Based on this setup [jobindjohn/obsidian-publish-mkdocs: A Template to Publish Obsidian/Foam Notes on Github Pages (uses MkDocs)](https://github.com/jobindjohn/obsidian-publish-mkdocs)
### Hosting & CI
Free hosting using [Cloudflare](https://www.cloudflare.com/)
Set ENV var PYTHON_VERSION to 3.7 and use this build command
```bash 
pip install --upgrade pip && pip install mkdocs-material && pip install mkdocs-roamlinks-plugin && pip install mkdocs-mermaid2-plugin && shopt -s extglob && mkdir docs && mv !(docs) ./docs/ && cp ./docs/mkdocs.yaml ./mkdocs.yaml && cp ./docs/README.md ./docs/index.md && mkdocs build
```

## Use Obsidian for Graph View
![[Pasted image 20221103175044.png]]