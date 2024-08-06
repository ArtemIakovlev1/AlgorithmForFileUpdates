<h1>Algorithm for file updates</h1>

<h2>Description</h2>
I am a `security` professional working at a health care company. As part of my job, I am required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an "allow_list.txt" file for IP addresses permitted to sign into the restricted subnetwork. There's also a remove_list that identifies which employees I must remove from this "allow_list.txt".
My task is to create an algorithm that uses Python code to check whether the "allow_list.txt" contains any IP addresses identified on the remove_list. If so, I should remove those IP addresses from the file containing the "allow_list.txt".

<h2>Languages</h2>

- <b>Python</b> 

<h3>Program walk-through:</h2>

```python
# Open the file that contains the allow list
import_file = "allow_list.txt"
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

with open(import_file, "r") as file:
    # Read the file contents
    ip_addresses = file.read()
    print(ip_addresses)

    # Convert the string into a list
    ip_addresses = ip_addresses.split()
    print(ip_addresses)

# Iterate through the remove list
for element in ip_addresses:
    print(element)

    # Remove IP addresses that are on the remove list
    if element in remove_list:
        ip_addresses.remove(element)

# Update the file with the revised list of IP addresses
ip_addresses = " ".join(ip_addresses)
with open(import_file, "w") as file:
    file.write(ip_addresses)
```



<h2>Summary</h2>
I created an algorithm that removes IP addresses identified in a remove_list variable from the "allow_list.txt" file of approved IP addresses. This algorithm involved opening the file, converting it to a string to be read, and then converting this string to a list stored in the variable "ip_addresses". I then iterated through the IP addresses in remove_list. With each iteration, I evaluated if the element was part of the ip_addresses list. If it was, I applied the .remove() method to it to remove the element from ip_addresses.. After this, I used the .join() method to convert the ip_addresses back into a string so that I could write over the contents of the "allow_list.txt" file with the revised list of IP addresses.
