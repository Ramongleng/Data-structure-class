#include <iostream>
#include <stack>
#include <queue>
#include <string>

int main() 
{
    while ( true )
    {
        std::string letters;
        std::cout << "Enter a word for palindrome check ";
        std::getline( std::cin, letters );

        if ( letters.empty() ) break;

        std::stack<char> 
            s( std::stack<char>::container_type( letters.begin(), letters.end() ) );
        std::queue<char> 
            q( std::queue<char>::container_type( letters.begin(), letters.end() ) );

        while ( !s.empty() && s.top() == q.front() )
        {
            s.pop();
            q.pop();
        }

        if ( s.empty() ) std::cout << "The word is a palindrome" <<std::endl;
        else std::cout << "The word is not a palindrome" << std::endl;
    }

    return 0;
}
