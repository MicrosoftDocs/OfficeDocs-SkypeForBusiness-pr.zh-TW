---
title: Lync Server 2013：刪除外部使用者存取的網站或使用者原則
description: Lync Server 2013：刪除外部使用者存取的網站或使用者原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aac81e7b50603e5eb80cde8877cdc06f138d872
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553709"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="7972d-103">在 Lync Server 2013 中刪除外部使用者存取的網站或使用者原則</span><span class="sxs-lookup"><span data-stu-id="7972d-103">Delete a site or user policy for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7972d-104">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7972d-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7972d-105">您可以刪除 [ **外部存取原則** ] 頁面上任何列于 [Lync Server 控制台] 中的網站或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="7972d-105">You can delete any site or user policy that is listed in Lync Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="7972d-106">刪除全域原則並不是實際加以刪除，只是將它重設為不支援任何外部使用者存取選項的預設設定。</span><span class="sxs-lookup"><span data-stu-id="7972d-106">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="7972d-107">如需重設全域原則的詳細資訊，請參閱 [在 Lync Server 2013 中重設外部使用者存取的全域原則](lync-server-2013-reset-the-global-policy-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="7972d-107">For details about resetting the global policy, see [Reset the global policy for external user access in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span></span>

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="7972d-108">刪除外部使用者存取的網站或使用者原則</span><span class="sxs-lookup"><span data-stu-id="7972d-108">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="7972d-109">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="7972d-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7972d-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="7972d-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7972d-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7972d-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7972d-112">按一下 **[外部使用者存取]**，並按一下 **[外部存取原則]**。</span><span class="sxs-lookup"><span data-stu-id="7972d-112">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="7972d-113">在 **[外部存取原則]** 索引標籤上，按一下想要刪除的網站或使用者原則，並按一下 **[編輯]**，然後按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="7972d-113">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="7972d-114">系統提示確認刪除時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7972d-114">When prompted to confirm the deletion, click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7972d-115">使用 Windows PowerShell Cmdlet 移除 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="7972d-115">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7972d-116">您可以使用 Windows PowerShell 和 Remove-CsExternalAccessPolicy Cmdlet 刪除外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="7972d-116">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="7972d-117">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7972d-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7972d-118">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="7972d-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="7972d-119">移除特定的外部存取原則</span><span class="sxs-lookup"><span data-stu-id="7972d-119">To remove a specific external access policy</span></span>

  - <span data-ttu-id="7972d-120">此命令會移除套用至 Redmond 網站的外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="7972d-120">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="7972d-121">移除所有套用至個別使用者範圍的外部存取原則</span><span class="sxs-lookup"><span data-stu-id="7972d-121">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="7972d-122">此命令會移除在個別使用者範圍內設定的外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="7972d-122">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="7972d-123">移除已停用外部使用者存取的所有外部存取原則</span><span class="sxs-lookup"><span data-stu-id="7972d-123">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="7972d-124">此命令會刪除已停用外部使用者存取的所有外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="7972d-124">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

<span data-ttu-id="7972d-125">如需詳細資訊，請參閱 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="7972d-125">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

