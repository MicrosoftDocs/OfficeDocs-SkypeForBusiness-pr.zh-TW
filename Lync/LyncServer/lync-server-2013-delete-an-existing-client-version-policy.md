---
title: Lync Server 2013：刪除現有的用戶端版本原則
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
ms.openlocfilehash: 99936b495075034e6eae3f90e6dd95325bf6e2be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="83ed9-102">刪除 Lync Server 2013 中的現有用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="83ed9-102">Delete an existing client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83ed9-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="83ed9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="83ed9-104">如果您想要刪除先前設定的用戶端版本原則，您可以從 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面] 中刪除。</span><span class="sxs-lookup"><span data-stu-id="83ed9-104">If you want to delete a client version policy that was previously configured, you can delete it from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="83ed9-105">使用 Lync Server 控制台刪除用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="83ed9-105">To delete client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="83ed9-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="83ed9-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="83ed9-107">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="83ed9-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="83ed9-108">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="83ed9-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="83ed9-109">在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**用戶端版本原則**] 瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="83ed9-109">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="83ed9-110">在 [**用戶端版本原則**] 頁面上，選取您要刪除的用戶端版本原則或原則，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="83ed9-110">On the **Client Version Policy** page, select the client version policy or policies you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="83ed9-111">使用 Windows PowerShell Cmdlet 刪除用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="83ed9-111">Deleting Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="83ed9-112">您可以使用**CsClientVersionPolicy** Cmdlet 刪除用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="83ed9-112">You can delete client version policies by using the **Remove-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="83ed9-113">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="83ed9-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="83ed9-114">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="83ed9-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-client-version-policy"></a><span data-ttu-id="83ed9-115">移除特定的用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="83ed9-115">To remove a specific client version policy</span></span>

  - <span data-ttu-id="83ed9-116">這個命令會刪除套用至雷德蒙者網站的用戶端版本原則：</span><span class="sxs-lookup"><span data-stu-id="83ed9-116">This command deletes the client version policy applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a><span data-ttu-id="83ed9-117">移除所有套用至網站範圍的用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="83ed9-117">To remove all the client version policies applied to the site scope</span></span>

  - <span data-ttu-id="83ed9-118">這個命令會移除在網站範圍中設定的所有用戶端版本原則：</span><span class="sxs-lookup"><span data-stu-id="83ed9-118">This command removes all the client version policies configured at the site scope:</span></span>
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a><span data-ttu-id="83ed9-119">若要移除不包含特定使用者代理程式的用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="83ed9-119">To remove client version policies that do not include a specific user agent</span></span>

  - <span data-ttu-id="83ed9-120">這個命令會移除任何不包含 Windows Phone Lync （WPLync）使用者代理程式規則的用戶端版本原則：</span><span class="sxs-lookup"><span data-stu-id="83ed9-120">And this command removes any client version policies that do not include a rule for the Windows Phone Lync (WPLync) user agent:</span></span>
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

<span data-ttu-id="83ed9-121">如需詳細資訊，請參閱[Remove CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="83ed9-121">For details, see the Help topic for the [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

