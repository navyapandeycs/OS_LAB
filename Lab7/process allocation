#include <stdio.h>

void allocate(int b[], int m, int p[], int n, int type)
{
    int a[n];

    for (int i = 0; i < n; i++)
        a[i] = -1;

    for (int i = 0; i < n; i++)
    {
        int idx = -1;

        for (int j = 0; j < m; j++)
        {
            if (b[j] >= p[i])   // block can fit process
            {
                if (type == 0)   // First Fit
                {
                    idx = j;
                    break;
                }

                if (type == 1)   // Best Fit
                {
                    if (idx == -1 || b[j] < b[idx])
                        idx = j;
                }

                if (type == 2)   // Worst Fit
                {
                    if (idx == -1 || b[j] > b[idx])
                        idx = j;
                }
            }
        }

        if (idx != -1)
        {
            a[i] = idx;
            b[idx] = -1;   // only ONE process per block
        }
    }

    if (type == 0) printf("\n--- First Fit ---\n");
    if (type == 1) printf("\n--- Best Fit ---\n");
    if (type == 2) printf("\n--- Worst Fit ---\n");

    printf("Process No.\tProcess Size\tBlock No.\n");

    for (int i = 0; i < n; i++)
    {
        printf("%d\t\t%d\t\t", i + 1, p[i]);

        if (a[i] != -1)
            printf("%d\n", a[i] + 1);
        else
            printf("Not Allocated\n");
    }
}

int main()
{
    int m, n;

    printf("Enter number of memory blocks: ");
    scanf("%d", &m);

    int b[m], b1[m], b2[m], b3[m];

    printf("Enter sizes of %d memory blocks:\n", m);

    for (int i = 0; i < m; i++)
    {
        scanf("%d", &b[i]);
        b1[i] = b2[i] = b3[i] = b[i];
    }

    printf("Enter number of processes: ");
    scanf("%d", &n);

    int p[n];

    printf("Enter sizes of %d processes:\n", n);

    for (int i = 0; i < n; i++)
        scanf("%d", &p[i]);

    allocate(b1, m, p, n, 0);
    allocate(b2, m, p, n, 1);
    allocate(b3, m, p, n, 2);

    return 0;
}
