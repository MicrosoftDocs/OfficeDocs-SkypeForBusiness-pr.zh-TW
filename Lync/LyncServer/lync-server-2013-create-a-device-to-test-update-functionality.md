---
title: Lync Server 2013：建立裝置以測試更新功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67712f981d8061b8dd3c90de812092e01dc5d1b5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="40e1c-102">在 Lync Server 2013 中建立裝置以測試更新功能</span><span class="sxs-lookup"><span data-stu-id="40e1c-102">Create a device to test update functionality in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40e1c-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="40e1c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="40e1c-104">您可以將測試裝置新增至 [ **測試裝置** ] 頁面，然後使用此裝置來確認新更新的功能，再將更新部署至實際執行裝置。</span><span class="sxs-lookup"><span data-stu-id="40e1c-104">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="40e1c-105">您可以在整個 Lync Server 環境) 或單一網站內，測試裝置全域 (。</span><span class="sxs-lookup"><span data-stu-id="40e1c-105">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="40e1c-106">您可以透過媒體存取控制來識別測試裝置 (MAC) 位址或序號。</span><span class="sxs-lookup"><span data-stu-id="40e1c-106">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="40e1c-107">當您新增裝置時，它會出現在 Lync Server 控制台的 [ **測試裝置** ] 頁面上的清單中。</span><span class="sxs-lookup"><span data-stu-id="40e1c-107">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="40e1c-108">新增測試裝置</span><span class="sxs-lookup"><span data-stu-id="40e1c-108">To add a test device</span></span>

1.  <span data-ttu-id="40e1c-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="40e1c-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="40e1c-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="40e1c-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="40e1c-111">在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **測試裝置**]。</span><span class="sxs-lookup"><span data-stu-id="40e1c-111">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="40e1c-112">按一下 [ **新增**]，然後按一下 [ **全域測試裝置** ] 或 [ **網站測試裝置**]。</span><span class="sxs-lookup"><span data-stu-id="40e1c-112">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="40e1c-113">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="40e1c-113">Do one of the following:</span></span>
    
      - <span data-ttu-id="40e1c-114">如果您已按一下 [ **全域測試裝置**]，請跳至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="40e1c-114">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="40e1c-115">如果您按一下 [ **網站測試裝置**]，請從可用網站清單中選取網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="40e1c-115">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="40e1c-116">在 [ **新增測試裝置**] 的 [ **裝置名稱**] 中，輸入裝置的名稱。</span><span class="sxs-lookup"><span data-stu-id="40e1c-116">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="40e1c-117">在 [ **識別碼類型**] 底下，按一下 [ **MAC 位址** 或 **序列碼**]。</span><span class="sxs-lookup"><span data-stu-id="40e1c-117">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="40e1c-118">在 [ **唯一識別碼** ] 方塊中，輸入裝置的 MAC 位址或序號。</span><span class="sxs-lookup"><span data-stu-id="40e1c-118">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="40e1c-119">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="40e1c-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="40e1c-120">使用 Windows PowerShell Cmdlet 建立測試裝置</span><span class="sxs-lookup"><span data-stu-id="40e1c-120">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="40e1c-121">您可以使用 Windows PowerShell 和 CsTestDevice Cmdlet 來建立測試裝置。</span><span class="sxs-lookup"><span data-stu-id="40e1c-121">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="40e1c-122">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="40e1c-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="40e1c-123">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="40e1c-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="40e1c-124">使用此 Cmdlet 建立測試裝置時，您必須執行下列兩項作業：</span><span class="sxs-lookup"><span data-stu-id="40e1c-124">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="40e1c-125">請以 IdentifierType 的形式指定 MACAddress 或 SerialNumber。</span><span class="sxs-lookup"><span data-stu-id="40e1c-125">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="40e1c-126">指定裝置身分識別時包含範圍。</span><span class="sxs-lookup"><span data-stu-id="40e1c-126">Include the scope when specifying the device Identity.</span></span> <span data-ttu-id="40e1c-127">若要在全域範圍內建立新的裝置，請使用類似下列的語法：</span><span class="sxs-lookup"><span data-stu-id="40e1c-127">To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="40e1c-128">若要在網站範圍建立測試裝置，請使用類似下列的語法：</span><span class="sxs-lookup"><span data-stu-id="40e1c-128">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="40e1c-129">使用 MAC 位址建立測試裝置</span><span class="sxs-lookup"><span data-stu-id="40e1c-129">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="40e1c-130">這個命令會在全域範圍中建立測試裝置，並使用 MAC 位址做為 IdentifierType：</span><span class="sxs-lookup"><span data-stu-id="40e1c-130">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="40e1c-131">使用序號建立測試裝置</span><span class="sxs-lookup"><span data-stu-id="40e1c-131">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="40e1c-132">這個命令會在 Redmond 網站) 的網站範圍 (建立新的測試裝置，並使用序數做為 IdentifierType：</span><span class="sxs-lookup"><span data-stu-id="40e1c-132">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="40e1c-133">如需詳細資訊，請參閱 [CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="40e1c-133">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

