---
title: "CDO Design"
excerpt: "<br/><img src='/images/wpi1.jpg'>"
collection: portfolio
permalink: /portfolio/portfolio-2
gallery1:
  - image_path: /cc1.jpg  
gallery2:
  - image_path: /c2.jpg   
gallery3:
  - image_path: /c3.jpg 
gallery4:
  - image_path: /c4.jpg 
gallery5:
  - image_path: /c5.jpg    
gallery6:
  - image_path: /c6.jpg 
gallery7:
  - image_path: /c7.jpg 

comments: true
---
Interest payments are always made annually at the beginning of each year. Losses resulting from defaults are always accounted for at the end of the year in which the default happens. (In financial language this means that the portfolio is "marked to the market" at the end of each year. Interest payments are made after the portfolio is marked to the market, which simply means that defaulted bonds don't pay interest.) By "interest" we always mean the sum of the annual risk free rate plus the corresponding credit spread.


The collateral pool for the CDO consists of 20 bonds with identical specifications:
Face value = 100 (thousand dollars),
                  Maturity = 5 years,
Credit spread = 500 bps (i.e. total annual interest = 9%).

It is assumed that the default times of the individual bonds are exponentially distributed. In other words, their hazard rates are constant. (These are the marginal distributions of default times.)


Regarding the joint distribution of the default times we will consider and compare seven scenarios.


As copulas, we will consider the Gaussian and the Student-t copula with 8 degrees of freedom.


We will assume that the default times are equi-correlated. In other words, the generating correlation matrix K will consist of all the same entries rho, except for the diagonal entries, which are always ones. Please note that the matrix K is the one that you will need to generate the joint distributions. (In case of the student distribution the resulting actual correlations also depend on nu, but this will not affect your calculations.) For rho we will consider the values 0.0, 0.2, 0.6 and 1.0. (For rho=1.0 the Student-t and Gaussian copulas are the same.)


The seven scenarios will be
     Gaussian copula with rho= 0, 0.2, 0.6 and 1.0
     Student-t copula with 8 degrees of freedom and rho= 0, 0.2 and  0.6.
 

The tranches of the CDO are set as follows:
     Equity=3/20,
     Mezzanine=5/20 and
     Senior=12/20.
In other words, the equity tranche is responsible to cover the losses of the first 3 defaulting bonds, the mezzanine tranche of the next 5 defaults (i.e. from the 4th default to the 8th default) and the senior tranche of the remaining 12 bonds. (The senior tranche is made much smaller than in real life to keep the size of the problem small.) We always assume zero recovery rate. In other words, if a bond defaults, then its entire face value is lost.


The CDO will be securitized as 20 securities (slices) each with $100(thousand) face value. This means that the equity tranche will be securitized as three slices of $100(thousand) each, the mezzanine tranche as 5 slices and the senior tranche as 12 slices. Investors wishing to buy a slice of the CDO will each have to pay $100(thousand). When a bond defaults, the affected investor class (equity, mezzanine or senior) will collectively lose the corresponding face value. (E.g. if a default affects the mezzanine tranche, then each of the five slices of that tranche will lose $20(thousand). In addition, all future interest payments to mezzanine investors will be reduced by 20% of their original annual interest.)
{% include gallery id="gallery1" class="full"  %}
{% include gallery id="gallery2" class="full"  %}
{% include gallery id="gallery3" class="full"  %}
{% include gallery id="gallery4" class="full"  %}
{% include gallery id="gallery5" class="full"  %}
{% include gallery id="gallery6" class="full"  %}
{% include gallery id="gallery7" class="full"  %}



