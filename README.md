# "Himbo", simple but pretty
## A class based interface to simplify prototyping programs with Tkinter GUIs 

Sometimes you write a program and you aren't that worried about what the GUI looks like. I started to get frustrated that every GUI element I coded with Tkinter needed to be styled individually. I felt like I was writing the same pieces of code over and over, even though the stylistic details I was coding weren't important to me on those projects. I wanted to be able to style tkinter objects en-masse the same way that CSS can code all similar elements of a piece of HTML.

The Panel class file is my attempt to simplify this process for myself. A version of it is dragged into every project where I want a very basic GUI with no frills. I set the styling options once at the top of the file. From this point onwards it acts as a template for all GUI elements I make. 

This class also simplifies the syntax for calling Tkinter objects into being. Rather than defining every element individually, elements of the same type are submitted to the class' functions as a list. The class then outputs the required elements with all styling in place.

Full explanation of the syntax is given in the file, but an example panel is included below to give a sense of the workflow. 

An instance of the class is called and named.

            panel = Panel()
            panel.title = "Text Analysis Utility"

Spaces and buttons for entering text are made by submitting a list of the intended titles for those entries. 

            panel.entries = [
                "Title",
                "Author",
                "Date",
            ]

File prompts, and information about how those file prompts should display, are submitted as a simple dictionary.

            panel.file_prompts = {
                "Text location": (("text file", "*.txt"), ("all files", "*.*")),
                "Database location": (("database file", "*db"),)
            }

As are buttons for triggering other functions.
            
            panel.buttons = {
                "About": About.as_popup_from(root),
                "Wiki": Wiki.as_popup_from(root)
            }

As this is a tool for helping me make other silly programs faster, I haven't put much effort into fully documenting the syntax. If someone else thinks they would find this a useful tool, reach out and I'll do my best to make a better readme.

