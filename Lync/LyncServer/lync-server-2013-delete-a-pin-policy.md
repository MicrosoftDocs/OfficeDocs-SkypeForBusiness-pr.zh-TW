---
title: Lync Server 2013：刪除 PIN 原則
description: Lync Server 2013：刪除 PIN 原則。
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
ms.openlocfilehash: 03e0f1d9c22e367693f846a31b1ad2232f048965
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566569"
---
# <a name="delete-a-pin-policy-in-lync-server-2013"></a><span data-ttu-id="d37f7-103">在 Lync Server 2013 中刪除 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="d37f7-103">Delete a PIN policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d37f7-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d37f7-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d37f7-105">遵循下列步驟，可刪除個人識別碼 (PIN) 原則。</span><span class="sxs-lookup"><span data-stu-id="d37f7-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d37f7-106">您無法刪除全域 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="d37f7-106">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a><span data-ttu-id="d37f7-107">在 Lync Server 2013 控制台中刪除 PIN 碼原則</span><span class="sxs-lookup"><span data-stu-id="d37f7-107">To delete a PIN policy in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="d37f7-108">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d37f7-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="d37f7-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d37f7-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d37f7-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d37f7-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d37f7-111">在左導覽列中，依序按一下 **[安全性]** 和 **[PIN 原則]**。</span><span class="sxs-lookup"><span data-stu-id="d37f7-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="d37f7-112">在 **[PIN 原則]** 頁面的搜尋欄位中，輸入您要刪除之原則的完整或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="d37f7-112">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="d37f7-113">在原則清單中，按一下您要的原則，再按一下 **[編輯]**，然後按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="d37f7-113">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="d37f7-114">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d37f7-114">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d37f7-115">使用 Windows PowerShell Cmdlet 移除 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="d37f7-115">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d37f7-116">您可以使用 Windows PowerShell 和 Remove-CsPinPolicy Cmdlet 來刪除 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="d37f7-116">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="d37f7-117">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d37f7-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d37f7-118">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="d37f7-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="d37f7-119">移除特定 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="d37f7-119">To remove a specific PIN policy</span></span>

  - <span data-ttu-id="d37f7-120">這個命令將移除含有 Identity RedmondPinPolicy 的 PIN 原則：</span><span class="sxs-lookup"><span data-stu-id="d37f7-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="d37f7-121">若要移除所有套用至網站範圍的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="d37f7-121">To remove all the PIN policies applied to the site scope</span></span>

  - <span data-ttu-id="d37f7-122">這個命令將移除網站範圍設定的所有 PIN 原則：</span><span class="sxs-lookup"><span data-stu-id="d37f7-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="d37f7-123">移除允許使用共同模式的所有 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="d37f7-123">To remove all the PIN policies that allow the use of common patterns</span></span>

  - <span data-ttu-id="d37f7-124">而且，這個將移除允許使用共同模式的所有 PIN 原則：G</span><span class="sxs-lookup"><span data-stu-id="d37f7-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

<span data-ttu-id="d37f7-125">如需詳細資訊，請參閱 [get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="d37f7-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

