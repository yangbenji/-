# -
//1
#include<stdio.h>
int main()
{
	int m[4][4]={0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0},i,j,x[4],y[4],z[4],w[4],l,q1,q2,q3,q4,q5,q6,q7,q8,q9,q10,q11,q12,t,q,u,k,n,p;
	int a[4],b[4],c[4],f[4],r[4][4];
	float d,e,o1,o2,o3,o4,g1,g2;
	scanf("%f %f %d %d %d %d",&d,&e,&l,&u,&t,&p) ;//机器，人数,x[0]从什么开始 ,终止于什么，招多少人 ,倍数 
	d=1.0*d/p;
	e=1.0*e/p;
	for(i=0;i<4;i++)
	{
		scanf("%d %d %d %d",&a[i],&b[i],&c[i],&f[i]) ;//人，机时，人工费,产量 
	}
	for(i=0;i<4;i++)
	{
		scanf("%d ",&x[i]) ;//初始数据 
	} 
	for(i=0;i<4;i++)
	{
		scanf("%d ",&y[i]) ;//初始数据 
	}
	for(i=0;i<4;i++)
	{
		scanf("%d ",&z[i]) ;//初始数据 
	}
	for(i=0;i<4;i++)
	{
		scanf("%d ",&w[i]) ;//初始数据 
	}
	q=0;//招多少人 
	k=(x[0]*c[0]+x[1]*c[1]+x[2]*c[2]+x[3]*c[3])*a[0]+(y[0]*c[0]+y[1]*c[1]+y[2]*c[2]+y[3]*c[3])*a[1]+(z[0]*c[0]+z[1]*c[1]+z[2]*c[2]+z[3]*c[3])*a[2]+(w[0]*c[0]+w[1]*c[1]+w[2]*c[2]+w[3]*c[3])*a[3]+q*1000/p;
	if(x[0]+x[1]>0) k=k+10000/p;//管理费
	if(x[3]+x[2]>0) k=k+12000/p;
	if(y[0]+y[1]>0) k=k+12000/p;//管理费 
	if(y[3]+y[2]>0) k=k+14000/p;
	if(z[0]+z[1]>0) k=k+15000/p;//管理费 
	if(z[3]+z[2]>0) k=k+18000/p;
	if(w[0]+w[1]>0) k=k+20000/p;//管理费 
	if(w[3]+w[2]>0) k=k+22000/p;
	printf("%d \n",k) ;
	for(;q<=t;q++) 
	{ 
		if(f[0]>d*520/b[0]) 
		{
			q1=d*520/b[0];
		}
		else q1=f[0] ;
		for(x[0]=l;x[0]<=u;x[0]++)
		{ 
			if(f[1]>(d*520-x[0]*b[0])/b[1]) 
			{
				q4= (d*520-x[0]*b[0])/b[1];
			} 
			else q4=f[1] ;
			printf("X1=%d ",x[0]) ;
			for(y[0]=0;y[0]<=q4;y[0]++)
			{
				if(f[2]>(d*520-x[0]*b[0]-y[0]*b[1])/b[2]) 
				{
					q7=(d*520-x[0]*b[0]-y[0]*b[1])/b[2];
				} 
				else q7=f[2];
				for(z[0]=0;z[0]<=q7;z[0]++)
				{
					if(f[3]>(d*520-x[0]*b[0]-y[0]*b[1]-z[0]*b[2])/b[3]) 
					{
						q10=(d*520-x[0]*b[0]-y[0]*b[1]-z[0]*b[2])/b[3];
					} 
					else q10=f[3]; 
					for(w[0]=0;w[0]<=q10;w[0]++)
					{
						if(x[0]*a[0]+y[0]*a[1]+z[0]*a[2]+w[0]*a[3]>(e+q*0.25/p)*520) break;
						if(f[0]-x[0]>d*260/b[0]) 
						{
							q2=d*260/b[0];
						} 
						else if(f[0]>x[0]) 
						{
							q2=f[0]-x[0];
						} 
						else q2=0;
						for(x[1]=0;x[1]<=q2;x[1]++) 
						{ 
							if(f[1]-y[0]>(d*260-x[1]*b[0])/b[1]) 
							{
								q5= (d*260-x[1]*b[0])/b[1];
							} 
							else if(f[1]>y[0]) 
							{
								q5=f[1]-y[0];
							} 
							else q5=0;
							for(y[1]=0;y[1]<=q5;y[1]++) 
							{  
								if(f[2]-z[0]>(d*260-x[1]*b[0]-y[1]*b[1])/b[2]) 
								{
									q8=(d*260-x[1]*b[0]-y[1]*b[1])/b[2];
								} 
								else if(f[2]>z[0]) 
								{
									q8=f[2]-z[0];
								}
								else q8=0;
								for(z[1]=0;z[1]<=q8;z[1]++) 
								{ 
									if(f[3]-w[0]>(d*260-x[1]*b[0]-y[1]*b[1]-z[1]*b[2])/b[3])
									{
										q11=(d*260-x[1]*b[0]-y[1]*b[1]-z[1]*b[2])/b[3];
									} 
									else if(f[3]>w[0])
									{
										q11=f[3]-w[0];
									} 
									else q11=0;
									for(w[1]=0;w[1]<=q11;w[1]++)
									{ 
										o1=(x[0]*a[0]+y[0]*a[1]+z[0]*a[2]+w[0]*a[3])/520.00;
										o2=(x[1]*a[0]+y[1]*a[1]+z[1]*a[2]+w[1]*a[3])/260.00;
										if(o2>o1)break; 
										if(x[1]*b[0]+y[1]*b[1]+z[1]*b[2]+w[1]*b[3]>d*260) break;
										if(f[0]-x[0]-x[1]>d*520/b[0]) 
										{
											q3=d*520/b[0] ;
										} 
										else if(f[0]-x[0]-x[1]>0) 
										{
											q3= f[0]-x[0]-x[1];
										} 
										else q3=0;
										for(x[2]=0;x[2]<=q3;x[2]++) 
										{
											x[3]=f[0]-x[0]-x[1]-x[2] ;
											if(f[1]-y[0]-y[1]>(d*520-x[2]*b[0])/b[1]) 
											{
												q6=(d*520-x[2]*b[0])/b[1];
											} 
											else if(f[0]-y[0]-y[1]>0) 
											{
												q6= f[1]-y[0]-y[1];
											} 
											else q6=0;
											for(y[2]=0;y[2]<=q6;y[2]++) 
											{
												y[3]=f[1]-y[0]-y[1]-y[2] ;
												if(f[2]-z[0]-z[1]>(d*520-x[2]*b[0]-y[2]*b[1])/b[2]) 
												{
													q9=(d*520-x[2]*b[0]-y[2]*b[1])/b[2];
												} 
												else if(f[2]-z[0]-z[1]>0) 
												{
													q9= f[0]-z[0]-z[1];
												} 
												else q9=0;
												for(z[2]=0;z[2]<=q9;z[2]++) 
												{
													z[3]=f[2]-z[0]-z[1]-z[2] ;
													if(f[3]-w[0]-w[1]>(d*520-x[2]*b[0]-y[2]*b[1]-z[2]*b[2])/b[3]) 
													{
														q12=(d*520-x[2]*b[0]-y[2]*b[1]-z[2]*b[2])/b[3];
													} 
													else if(f[3]-w[0]-w[1]>0) 
													{
														q12=f[3]-w[0]-w[1];
													} 
													else q12=0;
													for(w[2]=0;w[2]<=q12;w[2]++) 
													{
														w[3]=f[3]-w[0]-w[1]-w[2];
														o3=(x[2]*a[0]+y[2]*a[1]+z[2]*a[2]+w[2]*a[3])/520.00;
														o4=(x[3]*a[0]+y[3]*a[1]+z[3]*a[2]+w[3]*a[3])/260.00;
														if((x[1]*b[0]+y[1]*b[1]+z[1]*b[2]+w[1]*b[3])*2+x[2]*b[0]+y[2]*b[1]+z[2]*b[2]+w[2]*b[3]>d*520) break;
														if(x[3]*b[0]+y[3]*b[1]+z[3]*b[2]+w[3]*b[3]>d*260) continue;
														if(o3>(e+q*0.25/p)-o1) break;
														if(o4>o3) continue; 
														n=(x[0]*c[0]+x[1]*c[1]+x[2]*c[2]+x[3]*c[3])*a[0]+(y[0]*c[0]+y[1]*c[1]+y[2]*c[2]+y[3]*c[3])*a[1]+(z[0]*c[0]+z[1]*c[1]+z[2]*c[2]+z[3]*c[3])*a[2]+(w[0]*c[0]+w[1]*c[1]+w[2]*c[2]+w[3]*c[3])*a[3]+q*1000/p;
														
														if(x[0]+x[1]>0) n=n+10000/p;//管理费
														if(x[3]+x[2]>0) n=n+12000/p;
														if(y[0]+y[1]>0) n=n+12000/p;//管理费 
														if(y[3]+y[2]>0) n=n+14000/p;
														if(z[0]+z[1]>0) n=n+15000/p;//管理费 
														if(z[3]+z[2]>0) n=n+18000/p;
														if(w[0]+w[1]>0) n=n+20000/p;//管理费 
														if(w[3]+w[2]>0) n=n+22000/p;
														if(k>=n)
														{ 
															printf("\n%d %d %d %d ",x[0],x[1],x[2],x[3]);
															printf("%d %d %d %d ",y[0],y[1],y[2],y[3]);
															printf("%d %d %d %d ",z[0],z[1],z[2],z[3]);
															printf("%d %d %d %d %d ",w[0],w[1],w[2],w[3],n);
															for(i=0;i<4;i++)
															{ 
																m[0][i]=x[i];
																m[1][i]=y[i] ;
																m[2][i]=z[i];
																m[3][i]=w[i] ;
															}
															k=n;
														}		 
													} 
												} 
											} 
										} 
									}
								}
							}
						} 
					}
				}
			}
		}
		printf("\n招%d人\n",q) ;
	} 
	printf("结果为\n") ;
	for(i=0;i<4;i++)
	{
		for(j=0;j<4;j++)
		{
			printf("%d ",p*m[i][j]); 
		} 
		printf("\n") ;
	}
	printf("%d ",p*k) ;
}
