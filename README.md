# Full_Adder
module full_adder(
    input a,
    input b,
    input cin,
    output cout,
    output sum
    );
    assign sum = a^b^cin;
    assign cout = (a&b)|(b&cin)|(a&cin) ;
endmodule

module testbench;
reg a,b,cin;
wire sum,cout;
full_adder(a,b,cin,cout,sum);
initial
begin 
$monitor($time, " a = %b, b = %b, cin =%b, cout = %b, sum = %b",a,b,cin,cout,sum);
#5 a = 0; b = 0; cin = 1;
#5 a = 1;
#5 $finish;
end
endmodule
