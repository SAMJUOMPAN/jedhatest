{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {
    "colab_type": "text",
    "id": "1NCGks54kp_n"
   },
   "source": [
    "# How much do you get for your savings ?"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {
    "colab_type": "text",
    "id": "75Xe4f7vksGZ"
   },
   "source": [
    "It is said that if Christopher Columbus had set aside €1 that he had left at 2% interest per year, today his heirs would no longer need to work to live their lives. Let's try to calculate the same thing for our savings. "
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {
    "colab_type": "text",
    "id": "v4ugjwIakv2c"
   },
   "source": [
    "1. So let's create a function that will allow us to know how much money a user will have in total after a certain number of years.\n",
    "\n",
    "2. The user should be able to call the function which will then ask for :\n",
    "\n",
    "    1. The total amount he wishes to place\n",
    "    2. The number of years he wants to invest his money for\n",
    "    3. The rate of interest to which he is entitled\n",
    "    \n",
    "3. Pay attention to the errors that the user may enter.\n",
    "\n",
    "    4. If he enters a string of characters rather than a number, an error should be displayed.\n",
    "    5. If the user enters negative numbers, an error should also be output.\n",
    "    6. Finally, it is very likely that the user will write the interest rate as a percentage (e.g. 10%). Lift an error if this is the case to prevent him from putting a decimal number.\n",
    "    \n",
    "4. Finally, the program should only show one digit with a maximum of two digits after the decimal point.\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1,
   "metadata": {
    "colab": {
     "base_uri": "https://localhost:8080/",
     "height": 173
    },
    "colab_type": "code",
    "id": "ovkcocqXkp2k",
    "outputId": "c6b46d9b-3503-4490-f19a-4a7e35194eea"
   },
   "outputs": [],
   "source": [
    "def savings():\n",
    "    try:\n",
    "        amount_of_money = float(input(\"Which amount would you like to place ?\"))\n",
    "        number_of_years = float(input(\"How many years would you like to place it ?\"))\n",
    "        rate_of_interest = float(input(\"At which rate would you like to place your money ?\"))\n",
    "        \n",
    "        if (amount_of_money < 0 ) or (number_of_years < 0 ) or (rate_of_interest < 0 ) :\n",
    "            raise ValueError()\n",
    "            \n",
    "        interest = amount_of_money*rate_of_interest\n",
    "        gain = (interest + amount_of_money)*number_of_years\n",
    "    \n",
    "    except ValueError :\n",
    "        print(\"Please recall the function and only give positive numbers\")\n",
    "    \n",
    "    except ZeroDivisionError:\n",
    "        print(\"please comback teh function and give a number > 0\")\n",
    "        \n",
    "    else:\n",
    "            print(\"The amount of money you will have after you deposit {:4.2f} at the end of {:4.2f} years will be {:4.2f} €\".format(amount_of_money, number_of_years,gain))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "metadata": {
    "colab": {},
    "colab_type": "code",
    "id": "K_2poSknltX4"
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Which amount would you like to place ?10000\n",
      "How many years would you like to place it ?10\n",
      "At which rate would you like to place your money ?0.1\n",
      "The amount of money you will have after you deposit 10000.00 at the end of 10.00 years will be 110000.00 €\n"
     ]
    }
   ],
   "source": [
    "savings()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "colab": {
   "name": "Fondamentaux Python - Mini Projets S1-2B.ipynb",
   "provenance": [],
   "version": "0.3.2"
  },
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.8.3"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 1
}
