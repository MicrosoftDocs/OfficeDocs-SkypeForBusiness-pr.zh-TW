---
title: Lync Server 2013：啟用呼叫許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 864de6f8ac456ad8a312b5c47af1f19124e7be3f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="7586b-102">在 Lync Server 2013 中啟用呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="7586b-102">Enable call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7586b-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7586b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7586b-104">在您設定 [通話許可控制] 部署的網路設定之後，您必須啟用 CAC，才能使您的頻寬原則生效。</span><span class="sxs-lookup"><span data-stu-id="7586b-104">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>

<span data-ttu-id="7586b-105">如需詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="7586b-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="7586b-106">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="7586b-106">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [<span data-ttu-id="7586b-107">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="7586b-107">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [<span data-ttu-id="7586b-108">移除-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="7586b-108">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a><span data-ttu-id="7586b-109">使用管理命令介面啟用呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="7586b-109">To enable call admission control by using Management Shell</span></span>

1.  <span data-ttu-id="7586b-110">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="7586b-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7586b-111">執行 CsNetworkConfiguration Cmdlet 以在您的網路中啟用 CAC。</span><span class="sxs-lookup"><span data-stu-id="7586b-111">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network.</span></span> <span data-ttu-id="7586b-112">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="7586b-112">For example, run:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    <span data-ttu-id="7586b-113">如果您想要在網路中停用 CAC，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7586b-113">If you want to disable CAC in your network, run the following:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a><span data-ttu-id="7586b-114">使用 Lync Server [控制台] 啟用呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="7586b-114">To enable call admission control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7586b-115">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="7586b-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7586b-116">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7586b-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="7586b-117">在左側導覽列中，按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="7586b-117">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="7586b-118">按一下 [**全域**導覽] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7586b-118">Click the **Global** navigation button.</span></span>

4.  <span data-ttu-id="7586b-119">按一下清單中的 [**全域**]，然後選取 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="7586b-119">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="7586b-120">在 [**編輯全域設定**] 頁面上，選取 [**啟用通話許可控制**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7586b-120">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7586b-121">如果您想要在整個部署中停用 [呼叫許可控制]，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7586b-121">If you want to disable call admission control throughout your deployment, clear this check box.</span></span>

    
    </div>

6.  <span data-ttu-id="7586b-122">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7586b-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

