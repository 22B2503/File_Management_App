# File_Management_App
import os

def create_file(filename):
    try:
        with open(filenaem,'x') as f :
            print(f"File Name{filename}:Created Succesfully")
    except FileExistsError:
        print(F"File name {filename} aleardy exists")

    except Exception as E:
        print('an error occured') 

def view_all_files():
    files = os.listdr()                   
    if not files :
        print('no files found')
    else :
        print('Files in directory')
        for file in files :
            print(files)

def delete_file(filename):
    try:
        os.remove(filename)
        print(f'{filename} has been deleted successfully')
    except FileNotFoundError:
        print('file not found')
    except Exception as e:
        print('An error occured') 

def read_file(filename):
    try:
        with open('sample.txt','r') as f:
            content=f.read() 
            print(f"Content of '{filename} :\n{content}")
    except FileNotFoundError:
        print(f"{filename} doesnt exist")
    except Exception as e:
        print('An error occured')

def edit_file(filename):  
    try:
        with open('sample.txt','a') as f :
            content = input('Enter data to add =')
            f.write(content + "\n")
            print('Content added to {filenanme } sucessfully')
    except FileNotFoundError:
         print(f"{filename} doesnt exist")
    except Exception as e:
        print('An error occured')

def main ():
    while True:
         print('FILE MANAGEMENT APP')
         print('1 :Create files ')
         print('2 :View all files ') 
         print('3 :Delete files ')
         print('4 :Read  files ')
         print('5 :Edit files ')
         print('6 :Exit ')

         choice = input('Enter your choice(1-6) =')

         if choice =='1':
             filename = input("Enter the file-name to create =")
             create_file(filename)
         elif choice  =='2'   :
             view_all_files
         elif choice =='3' :
             filename=input('Enter your file name to delete')
             delete_file(filename)     
         elif choice =='4':
             filename=input('Enter file name to read')
             read_file(filename)
         elif choice =='5':
             filename=input('Enter file name to edit')
             edit_file(filename)
         elif choice=='6' :
             print('closingh the app....')
             break
         else :
             print('In-valid syntax')

if __name__ == "__main__"  :      
    main()    


     
