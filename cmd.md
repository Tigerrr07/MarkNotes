导出Markdown为PDF的命令
传统模板
```
pandoc --pdf-engine=xelatex -s -VCJKoptions=BoldFont="SimHei" -VCJKmainfont="SimSun" xxx.md -o xxx.pdf
```
进阶模板
```
pandoc --pdf-engine=xelatex --template=D:\MarkNotes\templates\pm-template.latex xxx.md -o xxx.pdf
```