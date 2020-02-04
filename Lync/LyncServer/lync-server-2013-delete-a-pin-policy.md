---
title: Lync Server 2013：刪除 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc11f1383ec652c512fe5542d9a6780ce028c516
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a><span data-ttu-id="e39d5-102">刪除 Lync Server 2013 中的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="e39d5-102">Delete a PIN policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e39d5-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e39d5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e39d5-104">請依照下列步驟刪除個人識別碼（PIN）原則。</span><span class="sxs-lookup"><span data-stu-id="e39d5-104">Follow these steps to delete a personal identification number (PIN) policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e39d5-105">您無法刪除全域 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="e39d5-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a><span data-ttu-id="e39d5-106">在 Lync Server 2013 的 [控制台] 中刪除 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="e39d5-106">To delete a PIN policy in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="e39d5-107">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e39d5-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="e39d5-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e39d5-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e39d5-109">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e39d5-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e39d5-110">在左側導覽列中，按一下 [**安全性**]，然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="e39d5-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="e39d5-111">在 [ **PIN 原則**] 頁面上，于 [搜尋] 欄位中，輸入您要刪除之原則的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="e39d5-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="e39d5-112">在原則清單中，按一下您想要的原則，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="e39d5-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="e39d5-113">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e39d5-113">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e39d5-114">使用 Windows PowerShell Cmdlet 移除 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="e39d5-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e39d5-115">您可以使用 Windows PowerShell 與 Remove CsPinPolicy Cmdlet 來刪除 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="e39d5-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="e39d5-116">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e39d5-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e39d5-117">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="e39d5-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="e39d5-118">移除特定的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="e39d5-118">To remove a specific PIN policy</span></span>

  - <span data-ttu-id="e39d5-119">這個命令會移除具有身分識別 RedmondPinPolicy 的 PIN 原則：</span><span class="sxs-lookup"><span data-stu-id="e39d5-119">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="e39d5-120">若要移除所有套用至網站範圍的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="e39d5-120">To remove all the PIN policies applied to the site scope</span></span>

  - <span data-ttu-id="e39d5-121">這個命令會移除在網站範圍中設定的所有 PIN 原則：</span><span class="sxs-lookup"><span data-stu-id="e39d5-121">This command removes all the PIN policies configured at the site scope:</span></span>
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="e39d5-122">若要移除所有允許使用常見模式的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="e39d5-122">To remove all the PIN policies that allow the use of common patterns</span></span>

  - <span data-ttu-id="e39d5-123">如此一來，會移除所有允許使用常見模式的 PIN 原則： G</span><span class="sxs-lookup"><span data-stu-id="e39d5-123">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

<span data-ttu-id="e39d5-124">如需詳細資訊，請參閱[Remove CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="e39d5-124">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

