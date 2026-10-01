<img width="635" height="142" alt="image" src="https://github.com/user-attachments/assets/451e5f17-b11a-41cc-98b9-3ebcddc2cf03" />
QUESTION:-
A. Letter
time limit per test1 second
memory limit per test64 megabytes
A boy Bob likes to draw. Not long ago he bought a rectangular graph (checked) sheet with n rows and m columns. Bob shaded some of the squares on the sheet. Having seen his masterpiece, he decided to share it with his elder brother, who lives in Flatland. Now Bob has to send his picture by post, but because of the world economic crisis and high oil prices, he wants to send his creation, but to spend as little money as possible. For each sent square of paper (no matter whether it is shaded or not) Bob has to pay 3.14 burles. Please, help Bob cut out of his masterpiece a rectangle of the minimum cost, that will contain all the shaded squares. The rectangle's sides should be parallel to the sheet's sides.

Input
The first line of the input data contains numbers n and m (1 ≤ n, m ≤ 50), n — amount of lines, and m — amount of columns on Bob's sheet. The following n lines contain m characters each. Character «.» stands for a non-shaded square on the sheet, and «*» — for a shaded square. It is guaranteed that Bob has shaded at least one square.
SOLUTION:-
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>

using namespace std;
int main(){
    int n,m;
    cin>>n>>m;
    vector<string>grid(n);
    for(int i=0;i<n;i++){
        cin>>grid[i];
    }
    int minrow=n,maxrow=-1;
    int mincol=m,maxcol=-1;
    for(int i=0;i<n;i++){
        for(int j=0;j<m;j++){
          if(grid[i][j]=='*'){
              minrow=min(minrow,i);
              maxrow=max(maxrow,i);
              mincol=min(mincol,j);
              maxcol=max(maxcol,j);
          }  
        }
    }
    for(int i=minrow;i<=maxrow;i++){
        for(int j=mincol;j<=maxcol;j++){
            cout<<grid[i][j];
        }
        cout<<'\n';
    }
    return 0;
}
