#include<stdio.h>

int main() {
    int n,m,i,j,k,c=0,f[10]={0},a[10][10],max[10][10],need[10][10],av[10],s[10];

    printf("Enter number of processes: ");
    scanf("%d",&n);

    printf("Enter number of resources: ");
    scanf("%d",&m);

    printf("\nEnter Allocation Matrix:\n");
    for(i=0;i<n;i++)
        for(j=0;j<m;j++)
            scanf("%d",&a[i][j]);

    printf("\nEnter Maximum Demand Matrix:\n");
    for(i=0;i<n;i++)
        for(j=0;j<m;j++) {
            scanf("%d",&max[i][j]);
            need[i][j]=max[i][j]-a[i][j];
        }

    printf("\nEnter Available Resources:\n");
    for(i=0;i<m;i++)
        scanf("%d",&av[i]);

    while(c<n) {
        int found=0;

        for(i=0;i<n;i++) {
            if(!f[i]) {

                for(j=0;j<m;j++)
                    if(need[i][j]>av[j]) break;

                if(j==m) {
                    for(k=0;k<m;k++)
                        av[k]+=a[i][k];

                    s[c++]=i;
                    f[i]=1;
                    found=1;
                }
            }
        }

        if(!found) {
            printf("\nSystem is not safe");
            return 0;
        }
    }

    printf("\nSystem is in a safe state.\n");
    printf("Safe sequence is: ");

    for(i=0;i<n;i++) {
        printf("P%d",s[i]);
        if(i<n-1) printf(" -> ");
    }
}
