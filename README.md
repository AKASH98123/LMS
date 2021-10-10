# LMS
Library Managment System 


list_of_books=["CV RAMAN","HC VERMA","MS CHAUHAN","N AVASTHI","PRILIPKO","VK JAISWAL"]
lend_books={}
class Library:
    _timing="You Can Only Acess Book From 9:00 AM To 6:00 PM From The Library"
    __rules="DO NOT SMOKE IN THE LIBRAARY \n DO NOT ABUSE IN THE LIBRARY \n DO NOT LOUD IN THE LIBRARY "
        
    def __init__(self,books_have,library_name):
        self.books_have=books_have
        self.library_name=library_name
    

    def display_books(self):
        print("WELCOME TO MY "+f"{self.library_name}")
        print("THESE BOOKS ARE AVAILABLE IN THE LIBRARY ::"+f"{self.books_have}")


    def lend():
        m=input("DO YOU WANT TO ACCESS THE BOOK ? ")
        if m=="yes" or "YES" or "Yes":
            which_book=input("ENTER WHICH BOOK U WANT TO ACCESS : ")
            name=input("ENTER YOUR NAME : ")
            if which_book in list_of_books:
                print("YES YOU CAN ACCESS THE BOOK.")
                list_of_books.remove(which_book)
                lend_books[f"{which_book}"]=name

                print("BOOKS REMAIN IN THE LIBRARY:: ",list_of_books)
                print("YOU LEND THE BOOK= ",lend_books)
            else:
                print("SORRY WE DONN'T HAVE THIS BOOK.")

        else:
            pass
    
    def donate():
        n=input("DO YOU WANT TO DONATE THE BOOK ? ")
        if n=="yes" or "YES" or "Yes":
            donate_name=input("PLZ ENTER YOUR NAME ")
            book_name=input("PLZ ENTER THE NAME OF THE BOOK ")
            if book_name in list_of_books:
                print("THANK YOU " +donate_name+ " BUT WE HAVE ALREADY HAVE THAT BOOK IN THE LIBRARY")
            else:
                list_of_books.append(book_name)
                print(list_of_books)
                print("THANK YOU FOR THE DONATION MAY GOD BLESS YOU .")

        elif n=="no" or "NO" or "No":
            print("THANK YOU FOR VISITING MY LIBRARY")
        else:
            print("PLZ SELECT yes/no")

    def return_book():
        print("PLZ FULLFILL THE FORMALITIES TO RETURN THE BOOK ")
        return_name=input("PLA ENTER YOUR NAME : ")
        return_books=input("PLZ ENTER BOOK NAME : ")
        if return_books in lend_books:
            list_of_books.append(return_books)
            print("THANKS FOR RETURNING THE BOOK")
            del lend_books[f"{return_books}"]
        else:
            print("PLZ RETURN CORRECT BOOK!!!!")    

akash=Library(list_of_books,"MOONSHINE LIBRARY")
# print(akash.display_books())

print("PRESS 1 FOR DISPLAY THE BOOKS WHICH ARE AVIALABLE IN THE LIBRARY ")
print("PRESS 2 FOR THE LEND THE BOOK ")
print("PRESS 3 FOR DONATE THE BOOK  ")
print("PRESS 4 FOR RETURN THE BOOK  ")

while True:
    a=int(input("PLZ CHOOSE THE NUMBER :: "))
    if a==1:
        akash.display_books()
    elif a==2:
        Library.lend()
    elif a==3:
        Library.donate()
    elif a==4:
        Library.return_book()
    else:
        print("PLZ CHOOSE VALID INPUT!!")

# print(Library._timing)------------>PROTECTED 
# print(akash._Library__rules)------>PRIVATE

