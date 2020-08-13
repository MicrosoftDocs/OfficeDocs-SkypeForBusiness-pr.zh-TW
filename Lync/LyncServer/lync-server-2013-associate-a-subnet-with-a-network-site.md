---
title: Lync Server 2013：將子網與網路網站建立關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6d41e5959eaf596faaed25a9759534a9156f0d9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a><span data-ttu-id="b7c58-102">在 Lync Server 2013 中建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="b7c58-102">Associate a subnet with a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7c58-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b7c58-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b7c58-104">您網路中的每個子網都必須與特定網路網站產生關聯，因為子網資訊是用來決定端點所在的網路網站，而啟動新的會話時。</span><span class="sxs-lookup"><span data-stu-id="b7c58-104">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="b7c58-105">在會話中每一方的位置已知時，「高級 Enterprise 語音功能」可以套用該資訊，決定如何處理通話設定或路由傳送。</span><span class="sxs-lookup"><span data-stu-id="b7c58-105">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b7c58-106">您部署中 Audio/Video Edge Server 的所有已設定公用 IP 位址，都必須新增至您的網路設定。</span><span class="sxs-lookup"><span data-stu-id="b7c58-106">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="b7c58-107">這兩個 IP 位址會新增為遮罩為32的子網。</span><span class="sxs-lookup"><span data-stu-id="b7c58-107">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="b7c58-108">相關聯的網路網站應該對應至適當設定的網站。</span><span class="sxs-lookup"><span data-stu-id="b7c58-108">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="b7c58-109">例如，與中央網站芝加哥的 A/V Edge Server 對應的公用 IP 位址，將會是 NetworkSiteID 芝加哥。</span><span class="sxs-lookup"><span data-stu-id="b7c58-109">For example, the public IP address that corresponds to the A/V Edge Server in central site Chicago would be NetworkSiteID Chicago.</span></span> <span data-ttu-id="b7c58-110">如需公用 IP 位址的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">決定 Lync Server 2013 的外部 A/V 防火牆和埠需求</A> 。</span><span class="sxs-lookup"><span data-stu-id="b7c58-110">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b7c58-111">會引發重要狀態指示器 (KHI) 通知，指定存在於您的網路中，但未與子網路相關聯，或包含 IP 位址的子網路未與網站相關聯的 IP 位址清單。</span><span class="sxs-lookup"><span data-stu-id="b7c58-111">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="b7c58-112">在8小時內，將不會多次引發此警示。</span><span class="sxs-lookup"><span data-stu-id="b7c58-112">This alert will not be raised more than once within an 8-hour period.</span></span> <span data-ttu-id="b7c58-113">以下是相關的通知資訊與範例：</span><span class="sxs-lookup"><span data-stu-id="b7c58-113">The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="b7c58-114"><STRONG>來源：</STRONG> CS 頻寬原則服務 (核心) </span><span class="sxs-lookup"><span data-stu-id="b7c58-114"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="b7c58-115"><STRONG>事件編號：</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="b7c58-115"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="b7c58-116"><STRONG>層級：</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="b7c58-116"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="b7c58-117"><STRONG>描述：</STRONG> 下列 IP 位址的子網： &lt; 未設定 Ip 位址的清單 &gt; ，或未將子網與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="b7c58-117"><STRONG>Description:</STRONG> The subnets for the following IP addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a Network Site.</span></span><BR><span data-ttu-id="b7c58-118"><STRONG>原因：</STRONG> 網路設定中遺失對應之 IP 位址的子網，也不會將子網與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="b7c58-118"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="b7c58-119"><STRONG>解決方法：</STRONG> 將對應至 IP 位址清單的子網新增至網路設定設定，並將每個子網與網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="b7c58-119"><STRONG>Resolution:</STRONG> Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="b7c58-120">例如，如果警示中的 IP 位址清單指定10.121.248.226 和10.121.249.20，則這些 IP 位址不會與子網產生關聯，或與其相關聯的子網不屬於網路網站。</span><span class="sxs-lookup"><span data-stu-id="b7c58-120">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site.</span></span> <span data-ttu-id="b7c58-121">如果 10.121.248.0/24 與 10.121.249.0/24 是這些位址的對應子網路，您可以透過下列方式解決此問題：</span><span class="sxs-lookup"><span data-stu-id="b7c58-121">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="b7c58-122">確定 IP 位址 10.121.248.226 與 10.121.248.0/24 子網路相關聯，而 IP 位址 10.121.249.20 與 10.121.249.0/24 子網路相關聯。</span><span class="sxs-lookup"><span data-stu-id="b7c58-122">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
> <LI>
> <P><span data-ttu-id="b7c58-123">確定 10.121.248.0/24 與 10.121.249.0/24 兩個子網路分別與一個網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="b7c58-123">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>



</div>

<span data-ttu-id="b7c58-124">如需使用網路子網的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b7c58-124">For details about working with network subnets, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="b7c58-125">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b7c58-125">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [<span data-ttu-id="b7c58-126">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b7c58-126">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [<span data-ttu-id="b7c58-127">CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b7c58-127">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [<span data-ttu-id="b7c58-128">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b7c58-128">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> <span data-ttu-id="b7c58-129">如果您使用的是大量子網，建議您使用以逗號分隔的值 (CSV) 檔案，以將子網與網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="b7c58-129">If you are working with a large number of subnets, we recommend using a comma-separated values (CSV) file to associate the subnets to sites.</span></span> <span data-ttu-id="b7c58-130">CSV 檔案必須具有下列四個欄： <STRONG>IPAddress</STRONG>、 <STRONG>mask</STRONG>、 <STRONG>description</STRONG>、 <STRONG>NetworkSiteID</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="b7c58-130">The CSV file must have the following four columns: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span></span>



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a><span data-ttu-id="b7c58-131">使用管理命令介面建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="b7c58-131">To associate a subnet with a network site by using Management Shell</span></span>

1.  <span data-ttu-id="b7c58-132">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b7c58-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b7c58-133">執行 **New-CsNetworkSubnet** Cmdlet 以將子網與網路網站產生關聯：</span><span class="sxs-lookup"><span data-stu-id="b7c58-133">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    <span data-ttu-id="b7c58-134">例如：</span><span class="sxs-lookup"><span data-stu-id="b7c58-134">For example:</span></span>
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    <span data-ttu-id="b7c58-135">在此範例中，您已建立子網172.11.12.13 與網路網站 "芝加哥" 之間的關聯性。</span><span class="sxs-lookup"><span data-stu-id="b7c58-135">In this example, you created an association between the subnet 172.11.12.13 and the network site “Chicago”.</span></span>

3.  <span data-ttu-id="b7c58-136">對拓撲中的所有子網重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="b7c58-136">Repeat step 2 for all subnets in your topology.</span></span>

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="b7c58-137">若要將子網與網站結合匯入 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="b7c58-137">To associate subnets with network sites by importing a CSV file</span></span>

1.  <span data-ttu-id="b7c58-138">建立包含您要新增之所有子網的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="b7c58-138">Create a CSV file that includes all of the subnets you want to add.</span></span> <span data-ttu-id="b7c58-139">例如，使用下列內容建立名為 **subnet.csv** 的檔案：</span><span class="sxs-lookup"><span data-stu-id="b7c58-139">For example, create a file named **subnet.csv** with the following content:</span></span>
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  <span data-ttu-id="b7c58-140">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b7c58-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b7c58-141">執行下列 Cmdlet 以匯入 **subnet.csv**，然後將其內容儲存在 Lync Server management store 中：</span><span class="sxs-lookup"><span data-stu-id="b7c58-141">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="b7c58-142">使用 Lync Server 控制台建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="b7c58-142">To associate a subnet with a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b7c58-143">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b7c58-143">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b7c58-144">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c58-144">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="b7c58-145">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="b7c58-145">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="b7c58-146">按一下 [ **子網** ] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="b7c58-146">Click the **Subnet** navigation button.</span></span>

4.  <span data-ttu-id="b7c58-147">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b7c58-147">Click **New**.</span></span>

5.  <span data-ttu-id="b7c58-148">在 [ **新建子網上** ] 頁面上，按一下 [ **子網識別碼**]，然後輸入您要與網路網站建立關聯之子網所定義之 IP 位址範圍中的第一個位址。</span><span class="sxs-lookup"><span data-stu-id="b7c58-148">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6.  <span data-ttu-id="b7c58-149">按一下 [ **遮罩**]，然後輸入要套用至子網的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="b7c58-149">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7.  <span data-ttu-id="b7c58-150">按一下 [ **網路網站識別碼**]，然後選取您要新增此子網的網站的網站識別碼。</span><span class="sxs-lookup"><span data-stu-id="b7c58-150">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7c58-151">如果您尚未建立網路網站，此清單將會是空的。</span><span class="sxs-lookup"><span data-stu-id="b7c58-151">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="b7c58-152">如需程式的詳細資訊，請參閱 <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify network site In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="b7c58-152">For details about the procedure, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="b7c58-153">您也可以執行 <STRONG>Get-CsNetworkSite</STRONG> Cmdlet，以取得部署的網站 IDs。</span><span class="sxs-lookup"><span data-stu-id="b7c58-153">You can also retrieve site IDs for your deployment by running the <STRONG>Get-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="b7c58-154">如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。</span><span class="sxs-lookup"><span data-stu-id="b7c58-154">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="b7c58-155">（選用）按一下 [ **描述**]，然後輸入其他資訊以描述這個子網。</span><span class="sxs-lookup"><span data-stu-id="b7c58-155">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9.  <span data-ttu-id="b7c58-156">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="b7c58-156">Click **Commit**.</span></span>

<span data-ttu-id="b7c58-157">重複這些步驟，將其他子網新增至網路網站。</span><span class="sxs-lookup"><span data-stu-id="b7c58-157">Repeat these steps to add other subnets to a network site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

