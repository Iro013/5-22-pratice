# 5-22-pratice
### A. 2163 초콜릿 자르기
'''
#include <stdio.h>

int main(){
    int n,m;
    
    scanf("%d %d",&n,&m);
    
    printf("%d",n*m-1);
    
    return 0;
}
'''
1*1에서는 1, 2*2에서는, 3 2*3에서는 5, 3*3에서는 8 이므로
n*m-1이라는 식이 나온다.

### B. 31866 손가락 게임

'''
#include <stdio.h>

int main(void) {
    int n,m;

    scanf("%d %d",&n,&m);

    if(n==m || ((n!=0&&n!=2&&n!=5&&m!=0&&m!=2&&m!=5)))
        printf("=");
    else if((n==0&&m==2)||(n==5&&m==0))
        printf(">");
    else if((n==2&&m==0)||(n==0&&m==5))
            printf("<");
    else{
        if((n==0&&n==2&&n==5)||(m!=0&&m!=2&&m!=5))
            printf(">");
        else if((n!=0&&n!=2&&n)||(5&&m==0&&m==2&&m==5))
            printf("<");
        else if(n<m)
            printf(">");
        else
            printf("<");
        
    }
    return 0;
}
'''
n,m의 값이 같거나 각 변수의 값이 0,2,5가 아닌 수이면 =를 출력을 하고
n또는 n이 0,2,5이 아닐때 반대 수가 이기도록 출력한 후
m,n값을 비교해서 결과를 출력한다.

### C. 31529 2024년에는 혼자가 아니길

'''
#include <stdio.h>

int main() {
    int x,y;
    
    scanf("%d %d",&x,&y);
    if(2*x-y<0){
        printf("-1");
        return 0;
    }
    printf("%d",2024*(2*x-y)/4);

    return 0;
}
'''
x와y값을 사용해서 W를 표현하면 w=(2x-y)/4이고 
w가 음수가 아니어야 하므로 2x-y<0일때 -1을 출력한다.

### D 31831 과민성 대장 증후군

'''
#include <stdio.h>

int main(void) {
  int n, m, count = 0, mod,sum=0;
  scanf("%d %d", &n, &m);

  for (int i = 0; i < n; i++) {
    scanf("%d",&mod);
      sum += mod;
      if(sum<0)
          sum=0;
      if(sum>=m)
          count++;
  }
    printf("%d",count);
  return 0;
}
'''
초기값 n,m을 입력받고 계속해서 mod값을 sum에 더해주고 sum값이 m보다 크면 count값에 1을 추가한다.

### E 31870 버블버블

'''
#include <stdio.h>

int main(void) {
    int n,i,j,cnt1=0,cnt2=1;
    long int arr1[1000],arr2[1000],temp;
    scanf("%d", &n);
    for(i=0;i<n;i++){
        scanf("%d",&arr1[i]);
    }
    for(i=0;i<n;i++){
        arr2[n-i-1]=arr1[i];
    }

    for(i=0;i<n-1;i++){
        for(j=i+1;j<n;j++){
            if(arr1[i]>arr1[j]){
                temp=arr1[i];
                arr1[i]=arr1[j];
                arr1[j]=temp;
                cnt1++;
            }
        }
    }
    for(i=0;i<n-1;i++){
        for(j=i+1;j<n;j++){
            if(arr2[i]>arr2[j]){
                temp=arr2[i];
                arr2[i]=arr2[j];
                arr2[j]=temp;
                cnt2++;
            }
        }
    }

    if(cnt1>cnt2)
        printf("%d",cnt2);
    else
        printf("%d",cnt1);
  return 0;
}
'''
버블정렬을 하다가 중간에 역순으로 바꾸면 횟수가 더 늘어나기 때문에 처음부터 바꿔서 다른 배열에 저장 후 더 횟수가 적은 값을 출력한다.
### F 31923 마라탕후루

'''
#include <stdio.h>

int main(void) {
  int n, p, q;
  int sb[100], sm[100];
  int count = 0;
  int a=0,b=0;
  scanf("%d %d %d", &n, &p, &q);

  for (int i = 0; i < n; i++) {
    scanf("%d", &sb[i]);
  }

  for (int i = 0; i < n; i++) {
    scanf("%d", &sm[i]);
  }
  
  while (count < 10000) {   
    
  }
  return 0;
}
'''
각 변수를 배열에 저장한 후 
### G 31936 밤양갱

'''
#include <stdio.h>

int main() {
  int n, t = 10, count = 1;

  scanf("%d", &n);

  for (int i = 1; i <= n; i += count) {
    t++;
    count *= 2;
  }
  printf("%d,%d", t, count);
  return 0;
}

'''

처음에 daldidalgo를 입력하는데 필요한 시간은 8초이고 마지막에 daldidan을 적을때 필요한 시간은 2초이므로
초기값을 10으로 선언한 후 daldidalgo의 개수가 2배씩 증가하므로 count를 2배해준다.
