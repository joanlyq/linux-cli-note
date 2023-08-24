* Check Existing Swap Space:
  1. First, determine the current swap space usage and identify the swap partition by executing the following command in the terminal:

  `sudo swapon --show`

  2. Turn Off the Swap:
  Before resizing the swap partition, you need to turn off the swap space. Execute the following command to disable the swap:

  `sudo swapoff -v /dev/{swap_partition}`



  3. If your Linux system doesn't have a dedicated swap partition or you prefer a more flexible approach, you can create a swap file. Follow these steps:

    > Determine File Size:
    > Decide on the desired size for the swap file. Consider the amount of RAM and the workload you typically run on your system.
    > For example, if your system has 4 GB of RAM, you might choose a swap file size of 4 GB.
    
* Create a Swap File:
  1. Use the fallocate command to create an empty file of the desired size. Execute the following command:

    `sudo fallocate -l {swap_file_size} /path/to/swapfile`

    > Replace {swap_file_size} with the desired size (e.g., 4G) and /path/to/swapfile with the path where you want to create the swap file.

  2. Set File Permissions: Restrict the swap file's access permissions to prevent unauthorized modifications. Execute the following command:

  `sudo chmod 600 /path/to/swapfile`

    > Replace /path/to/swapfile with the actual path of the swap file.

  3. Format the Swap File: Format the newly created file as swap space by executing the following command:

  `sudo mkswap /path/to/swapfile`
  > Replace /path/to/swapfile with the actual path of the swap file.

  4. Enable the Swap File: Enable the swap file by executing the following command:

  `sudo swapon /path/to/swapfile`

  > Replace /path/to/swapfile with the actual path of the swap file.


Reference: <https://www.scaler.com/topics/how-to-increase-swap-space-in-linux/>
