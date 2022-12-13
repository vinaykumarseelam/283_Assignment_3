# 283_Assignment_3

SJSU ID : 016040648
Name : Vinay Kumar Reddy Seelam

SJSU ID : 016043118
Name : Mohammad Javeed Sanganakal

1.For each member in your team, provide 1 paragraph detailing what parts of the lab that member implemented / researched.

Vinay Kumar Reddy Seelam

Modified & vmx.c file according to assignment-3, Added nested virtualisation, Tested output

Mohammad Javeed Sanganakal

Modified cpuid.c and researched which code can be modified and whats required for assignment-3 . Tested Output

2. Describe in detail the steps you used to complete the assignment. Consider your reader to be someone skilled in software development but otherwise unfamiliar with the assignment. Good answers to this question will be recipes that someone can follow to reproduce your development steps.

Step1: use the VM environment of assignment2

Step2: modify cpuid.c under arch/x86/kvm to add new feature: leaf function 0x4ffffffe, which return the exist number. And the exits number was counted in vmx.c under arch/x86/kvm/vmx.

Step3: rebuild the new linux kernel using make command：sudo make -j 2 modules && sudo make -j 2 && sudo make modules_install && sudo make install;

Step4: reboot the machine;

Step5: using virt-manager to enter the inner vm and run the test file on inner vm;

Step6: run the test code and get the output:

![image](https://github.com/vinaykumarseelam/283_Assignment_3/blob/main/Img1.jpeg)

![image](https://github.com/vinaykumarseelam/283_Assignment_3/blob/main/Img2.jpeg)

![image](https://github.com/vinaykumarseelam/283_Assignment_3/blob/main/Img3.jpeg)

![image](https://github.com/vinaykumarseelam/283_Assignment_3/blob/main/Img4.jpeg)

3.Comment on the frequency of exits – does the number of exits increase at a stable rate? Or are there more exits performed during certain VM operations? Approximately how many exits does a full VM boot entail?

Approximately 5116977. Number of exits are not stable and keeps changing. It depends on the activities performed on VM.

4.Of the exit types defined in the SDM, which are the most frequent? Least?

Exit 1: External Interrupt, Exit 30: IO Interrupt, Exit 32:WRMSR, Exit 48:EPT Violation are the Most Frequently occuring. Exit 29: MOV DR, Exit 46: Access to IDTR, Exit 55 XSETBV are the Least Frequently occuring.



