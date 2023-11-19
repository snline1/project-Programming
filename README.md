# project-Programming
#Programming project for Coulomb's law
#shahad nabil aldossari /2210003677
#SUMAYAH ALMARGHUOB / 2200003286
#Fatima al-Marar /22210003682 
#Randa alghamdi / 2190005914
#Sadeem alkhamis/2210003644 
#Equation
import sympy as sym
from sympy import symbols
q1, q2, r, k = symbols('q1 q2 r k')
F = k*q1*q2/r**2
F
import pandas as pd
data = {
    'Charge one':[3,3,3,3,3,3,3,3],
    'Charge two':[6,6,6,6,6,6,6,6],
    'Distance':[0.03,0.04,0.05,0.06,0.07,0.08,0.09,0.1],
    'Distance_square':[0.03**2,0.04**2,0.05**2,0.06**2,0.07**2,0.08**2,0.09**2,0.1**2]
}
 
df=pd.DataFrame(data) 
df
#final result
import pandas as pd
def Force(q1, q2, r, k=9 * 10**9):
    F= k * q1 *10**-6* q2*10**-6/(r**2)
    return F

df['Force']=Force(df['Charge one'],df['Charge two'],df['Distance'])
df=pd.DataFrame(df)
df
#graph
import matplotlib.pyplot as plt 
x=df.Distance_square
y=df.Force
plt.plot(x,y,color="b")
plt.xlabel("Distance r²(m²)")
plt.ylabel("Force(N)")
plt.title("Graph 1. The relationship between Distance and Force ",fontsize=15)
plt.text(0.006,100000,'$F=\\frac{k q1 q2}{r^2}$',fontsize=20)
plt.show()
