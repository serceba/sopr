// This source code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
// © MJShahsavar

//@version=5
indicator("BTC Leading SOPR: Onchain", timeframe = "W")
R = input.symbol("BTC_SOPR", "Symbol")
src = request.security(R, 'D', close)
D = ta.sma(src, 10)
M = ta.sma(src, 100)
G= D-M
h1= hline (0.02)
h2=hline (0.01)
h3= hline (0.0,  linewidth=2)
h4= hline (-0.01)
h5= hline (-0.02)

fill (h1, h2, color.red, transp = 60)
fill (h2, h3, color.orange, transp = 60)
fill (h3, h4, color.aqua, transp = 60)
fill (h4, h5, color.blue, transp = 60)

plot (G, color= color.blue ,  linewidth=1)
