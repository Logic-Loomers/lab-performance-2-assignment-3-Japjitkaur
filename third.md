Assume you oversee a small library and would like to develop a program that looks up books using their ISBNs. A list of books with their corresponding ISBN digits is in front of you. After the librarian inputs an ISBN, your software will look through the list to locate the relevant book.  The book's title and other details will be shown if the book is located. A notice stating that the book is not available in the library will appear if it cannot be located.
#include <iostream>
#include <map>
#include <string>

int main() {
    std::map<std::string, std::string> bookMap;
    bookMap["9780132350884"] = "The C++ Programming Language";
    bookMap["9780321563842"] = "Effective C++";
    bookMap["9780201633610"] = "Design Patterns";
    std::string inputISBN;
    std::cout << "Enter the ISBN: ";
    std::cin >> inputISBN;
    auto bookIterator = bookMap.find(inputISBN);
    if (bookIterator != bookMap.end()) {
        std::cout << "Book Title: " << bookIterator->second << std::endl;
    } else {
        std::cout << "Book not available in the library." << std::endl;
    }

    return 0;
}
