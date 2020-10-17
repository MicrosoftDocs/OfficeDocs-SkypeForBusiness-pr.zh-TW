---
title: Lync Server 2013：刪除現有的用戶端版本原則
description: Lync Server 2013：刪除現有的用戶端版本原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1328d54790b2a7856fa2776bb59feeb515bab1cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553659"
---
# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="d890e-103">在 Lync Server 2013 中刪除現有的用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="d890e-103">Delete an existing client version policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d890e-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d890e-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d890e-105">如果您想要刪除先前設定的用戶端版本原則，您可以從 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面中刪除它。</span><span class="sxs-lookup"><span data-stu-id="d890e-105">If you want to delete a client version policy that was previously configured, you can delete it from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="d890e-106">使用 Lync Server 控制台刪除用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="d890e-106">To delete client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d890e-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d890e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d890e-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d890e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d890e-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d890e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d890e-110">在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **用戶端版本原則** ] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="d890e-110">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="d890e-111">在 [ **用戶端版本原則** ] 頁面上，選取您要刪除的用戶端版本原則，按一下 [ **編輯**]，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="d890e-111">On the **Client Version Policy** page, select the client version policy or policies you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d890e-112">使用 Windows PowerShell Cmdlet 刪除用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="d890e-112">Deleting Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d890e-113">您可以使用 **Remove-CsClientVersionPolicy** Cmdlet 刪除用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="d890e-113">You can delete client version policies by using the **Remove-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="d890e-114">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d890e-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d890e-115">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="d890e-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-client-version-policy"></a><span data-ttu-id="d890e-116">移除特定用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="d890e-116">To remove a specific client version policy</span></span>

  - <span data-ttu-id="d890e-117">這個命令會刪除套用至 Redmond 網站的用戶端版本原則：</span><span class="sxs-lookup"><span data-stu-id="d890e-117">This command deletes the client version policy applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a><span data-ttu-id="d890e-118">移除套用至網站範圍的所有用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="d890e-118">To remove all the client version policies applied to the site scope</span></span>

  - <span data-ttu-id="d890e-119">此命令會移除在網站範圍設定的所有用戶端版本原則：</span><span class="sxs-lookup"><span data-stu-id="d890e-119">This command removes all the client version policies configured at the site scope:</span></span>
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a><span data-ttu-id="d890e-120">移除不包含特定使用者代理程式的用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="d890e-120">To remove client version policies that do not include a specific user agent</span></span>

  - <span data-ttu-id="d890e-121">而且，此命令會移除任何不含 Windows Phone Lync (WPLync) 使用者代理程式規則的用戶端版本原則：</span><span class="sxs-lookup"><span data-stu-id="d890e-121">And this command removes any client version policies that do not include a rule for the Windows Phone Lync (WPLync) user agent:</span></span>
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

<span data-ttu-id="d890e-122">如需詳細資訊，請參閱 [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="d890e-122">For details, see the Help topic for the [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

