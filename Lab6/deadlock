#include<stdio.h>

int main() {
    int n,m,i,j,k,f[10]={0},a[10][10],r[10][10],av[10],found;

    printf("Enter number of processes: ");
    scanf("%d",&n);

    printf("Enter number of resources: ");
    scanf("%d",&m);

    printf("\nEnter Allocation Matrix:\n");
    for(i=0;i<n;i++)
        for(j=0;j<m;j++)
            scanf("%d",&a[i][j]);

    printf("\nEnter Request Matrix:\n");]'
    for(i=0;i<n;i++)
        for(j=0;j<m;j++)
            scanf("%d",&r[i][j]);

    printf("\nEnter Available Resources:\n");
    for(i=0;i<m;i++)
        scanf("%d",&av[i]);

    do {
        found=0;

        for(i=0;i<n;i++) {
            if(!f[i]) {

                for(j=0;j<m;j++)
                    if(r[i][j]>av[j]) break;

                if(j==m) {
                    for(k=0;k<m;k++)
                        av[k]+=a[i][k];

                    f[i]=1;
                    found=1;
                }
            }
        }

    } while(found);

    int d=0;

    printf("\nProcesses in Deadlock:\n");

    for(i=0;i<n;i++)
        if(!f[i]) {
            printf("P%d ",i);
            d=1;
        }

    if(!d)
        printf("No deadlock detected. All processes can finish.");
}
