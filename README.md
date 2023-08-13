# What if Sherlock Holmes was a data scientist?
  
# calculate P(H|E) as function of
# P(H): The probability of the Hypothesis is true (the prior).
# P(E|H): The probability of the evidence to occur given that the Hypothesis is true (The likelihood)
# P(E|H is false) The probability of the evidence to occur given that the Hypothesis is False 
 
def calculate_bayes_theorem(p_H, p_E_given_H, p_E_given_H_is_false):
        p_H_is_false = 1 - p_H
        p_E = (p_E_given_H_is_false * p_H_is_false) + (p_E_given_H * p_H ) 
        try: 
            p_H_given_E = (p_E_given_H * p_H) / p_E
             
            # printing results
            print(f'P(H) = {p_H * 100}%')
            print(f'P(E|H) = {p_E_given_H * 100}%')
            print(f'P(E|H is false) = {p_E_given_H_is_false * 100}%')
            print(f'P(H|E) = {round(p_H_given_E,2) * 100}%')
 
            return p_H_given_E
         
        except ZeroDivisionError:
            print(f'ERROR: P(E) is equal to 0')
             
          
# P(H) 
# There is someone behind the curtains 'the prior' or 'probability of the Hypothesis is true'.
p_H = 0.1
 
# P(E|H)
# Hearing a noise from behind the curtains, given there is someone there, 'the likelihood'
p_E_given_H = 0.6
 
# P(E|H is false)
# hearing some noises from behind the curtains given that There is no one there.
p_E_given_H_is_false = 0.2
 
# calculate P(H|E)
result = calculate_bayes_theorem(p_H, p_E_given_H, p_E_given_H_is_false)
