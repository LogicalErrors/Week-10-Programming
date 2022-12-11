# Week-10-Programming
Week 10 Programming code

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
//Ryan Bain
//ITD-1253-60498
//11-15-2022
namespace Module10Progress
{
    
    public partial class frmRadioStar : Form
    {
        double number1 = 0;
        double number2 = 0;
        double result = 0;
        string operation = "";
        public frmRadioStar()
        {
            InitializeComponent();
            radioAddition.Checked = true;
            operation = "+";
        }

        private void btnExit_Click(object sender, EventArgs e)
        {
            this.Close();
        }

        private void btnReset_Click(object sender, EventArgs e)
        {
            txtBoxOpperand1.Text = "";
            txtBoxOpperand2.Text = "";
            txtBoxOpperand1.Focus();
            label3.Text = "";
            checkBox1.Checked = true;
            radioAddition.Checked = true;
        }

        private void label1_Click(object sender, EventArgs e)
        {

        }

        private void btnCalculate_Click(object sender, EventArgs e)
        {
            bool number1Ok = double.TryParse(txtBoxOpperand1.Text, out number1);
            bool number2Ok = double.TryParse(txtBoxOpperand2.Text, out number2);

            if (!(number1Ok))
            {
                label3.Text = "Please enter a valid Integer in both Textboxes";
                return;
            }
            else if (!(number2Ok))
            {
                label3.Text = "Please enter a valid Integer in boh TextBoxes";
                return;
            }
            else
            {
                switch (operation)
                {
                    case "+":
                        if (checkBox1.Checked == true)
                        {
                            
                            
                            result = number1 + number2;
                            label3.Text = result.ToString();
                            label3.Text = txtBoxOpperand1.Text +" + "+ txtBoxOpperand2.Text +" = "+ result;

                        }
                        else
                        {
                            result = number1 + number2;
                            label3.Text = result.ToString();
                            label3.Text = "The answer is" +" " +  result;
                        }
                        
                        break;
                  
                    case "-":
                        if (checkBox1.Checked == true)
                        {
                            result = number1 - number2;
                            label3.Text = result.ToString();
                            label3.Text = txtBoxOpperand1.Text + " - " + txtBoxOpperand2.Text +" = " + result;
                        }
                        else
                        {
                            result = number1 - number2;
                            label3.Text = result.ToString();
                            label3.Text = "The answer is" + " " + result;
                        }
                                
                        break;

                    case "*":
                        if (checkBox1.Checked == true)
                        {


                            result = number1 * number2;
                            label3.Text = result.ToString();
                            label3.Text = txtBoxOpperand1.Text + " * " + txtBoxOpperand2.Text + " = " + result;
                        }
                        else
                        {
                            result = number1 * number2;
                            label3.Text = result.ToString();
                            label3.Text = "The answer is" + " " + result;
                        }
                        break;

                    case "/":

                            if (checkBox1.Checked == true)
                            {
                                result = number1 / number2;
                                label3.Text = result.ToString();
                                label3.Text = txtBoxOpperand1.Text + " / " + txtBoxOpperand2.Text + " = " + result;
                            }
                            else 
                            {
                               result = number1 / number2;
                               label3.Text = result.ToString();
                               label3.Text = "The answer is" + " " + result;
                                
                            } 
                            
                          break;
                        
                        
                    case "%":
                        if (number2 != 0)
                        {
                            result = number1 % number2;
                            label3.Text = result.ToString();

                        }
                        else
                        {
                            label3.Text = "You can't preform a Modulus Operation with a 0";
                        }
                        break;
                       
                }
                

            }

        }

        private void lblMessage_Click(object sender, EventArgs e)
        {

        }

        private void checkBox1_CheckedChanged(object sender, EventArgs e)
        {

        }

        private void txtBoxOpperand1_TextChanged(object sender, EventArgs e)
        {

        }

        private void txtBoxOpperand2_TextChanged(object sender, EventArgs e)
        {

        }

        private void radioAddition_CheckedChanged(object sender, EventArgs e)
        {
            operation = "+";
        }

        private void radioSubtraction_CheckedChanged(object sender, EventArgs e)
        {
            operation = "-";

        }

        private void radioMultiplication_CheckedChanged(object sender, EventArgs e)
        {
            operation = "*";

        }

        private void radioDivision_CheckedChanged(object sender, EventArgs e)
        {
            operation = "/";

        }

        private void radioModulus_CheckedChanged(object sender, EventArgs e)
        {
            operation = "%";

        }
    }
}
