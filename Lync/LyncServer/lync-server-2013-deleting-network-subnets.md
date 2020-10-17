---
title: Lync Server 2013：刪除網路子網
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 013de3ae58424473aa42aee767982fd84a9d651e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504270"
---
# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="fbaf7-102">在 Lync Server 2013 中刪除網路子網</span><span class="sxs-lookup"><span data-stu-id="fbaf7-102">Deleting network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbaf7-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fbaf7-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fbaf7-104">您可以使用下列程式來刪除子網。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-104">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="fbaf7-105">在 [Lync Server 控制台] 中，您可以建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="fbaf7-106">如需建立或修改網路子網的詳細資訊，請參閱 [在 Lync Server 2013 中建立或修改網路子網](lync-server-2013-create-or-modify-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-106">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="fbaf7-107">在大多數安裝通話許可控制 (CAC) 的 Microsoft Lync Server 2013 中，通常會有大量子網。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-107">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="fbaf7-108">因此，通常最好是從 Lync Server 管理命令介面來設定子網。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-108">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="fbaf7-109">從那裡，您可以將 **New-CsNetworkSubnet** 與 Windows PowerShell Cmdlet 匯 **入-CSV**搭配呼叫。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-109">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="fbaf7-110">透過這些 Cmdlet 一起使用，您可以從逗點分隔的值讀取子網設定 ( .csv) 檔案，並同時建立多個子網。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-110">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="fbaf7-111">如需如何從 .csv 檔案建立子網的範例，請參閱 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-111">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="fbaf7-112">若要刪除網路子網</span><span class="sxs-lookup"><span data-stu-id="fbaf7-112">To delete a network subnet</span></span>

1.  <span data-ttu-id="fbaf7-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fbaf7-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fbaf7-115">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fbaf7-116">在左導覽列中，依序按一下 **[網路設定]** 和 **[子網路]**。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-116">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="fbaf7-117">在 [ **子網** ] 頁面上，按一下您要刪除的子網。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-117">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fbaf7-118">您可以一次刪除一個以上的子網。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-118">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="fbaf7-119">若要執行此動作，請按住 CTRL 鍵並選取多個子網，然後按住 CTRL 鍵。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-119">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="fbaf7-120">或者，若要選取所有子網，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-120">Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="fbaf7-121">在 **[編輯]** 功能表中，按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="fbaf7-122">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbaf7-122">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fbaf7-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fbaf7-123">See Also</span></span>


[<span data-ttu-id="fbaf7-124">在 Lync Server 2013 中建立或修改網路子網</span><span class="sxs-lookup"><span data-stu-id="fbaf7-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

