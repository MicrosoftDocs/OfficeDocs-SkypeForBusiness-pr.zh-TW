---
title: 刪除現有的用戶端版本設定的集合
description: 刪除現有的用戶端版本設定的集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25a7d384bdfd84a1a6e04041988c16788a116626
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572879"
---
# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f7851-103">在 Lync Server 2013 中刪除現有的 client version configuration 設定集合</span><span class="sxs-lookup"><span data-stu-id="f7851-103">Delete an existing collection of client version configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7851-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f7851-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f7851-105">如果您想要移除先前為網站設定的用戶端設定設定，您可以從 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面中移除設定。</span><span class="sxs-lookup"><span data-stu-id="f7851-105">If you want to remove the client configuration settings that have been previously configured for a site, you can remove the settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="f7851-106">使用 Lync Server 控制台移除用戶端設定設定</span><span class="sxs-lookup"><span data-stu-id="f7851-106">To remove client configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f7851-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f7851-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f7851-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f7851-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f7851-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f7851-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f7851-110">在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **用戶端版本** 設定] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="f7851-110">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="f7851-111">選取網站，依序按一下 [ **編輯**] 及 [ **刪除**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f7851-111">Select the site, click **Edit**, click **Delete**, and then click **OK**.</span></span>

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f7851-112">使用 Windows PowerShell Cmdlet 移除用戶端版本設定設定</span><span class="sxs-lookup"><span data-stu-id="f7851-112">Removing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f7851-113">您可以使用 **set-csclientversionconfiguration** Cmdlet 刪除用戶端版本設定設定。</span><span class="sxs-lookup"><span data-stu-id="f7851-113">You can delete client version configuration settings by using the **Remove-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="f7851-114">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f7851-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f7851-115">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="f7851-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a><span data-ttu-id="f7851-116">移除指定的用戶端版本設定集合</span><span class="sxs-lookup"><span data-stu-id="f7851-116">To remove a specified collection of client version configuration settings</span></span>

  - <span data-ttu-id="f7851-117">下列命令會移除套用至 Redmond 網站的用戶端版本設定：</span><span class="sxs-lookup"><span data-stu-id="f7851-117">The following command removes the client version configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="f7851-118">若要移除所有套用至網站範圍的用戶端版本設定設定</span><span class="sxs-lookup"><span data-stu-id="f7851-118">To remove all the client version configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="f7851-119">此命令會移除在網站範圍設定的所有用戶端版本設定：</span><span class="sxs-lookup"><span data-stu-id="f7851-119">This command removes all the client version configuration settings configured at the site scope:</span></span>
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a><span data-ttu-id="f7851-120">根據 DefaultAction 屬性值移除所有用戶端版本設定設定</span><span class="sxs-lookup"><span data-stu-id="f7851-120">To remove all the client version configuration settings based on the value of the DefaultAction property</span></span>

  - <span data-ttu-id="f7851-121">而且，此命令會移除所有已設定預設動作為 "Block" 的用戶端版本設定：</span><span class="sxs-lookup"><span data-stu-id="f7851-121">And this command removes all the client version configuration settings where the default action has been set to "Block":</span></span>
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

<span data-ttu-id="f7851-122">如需詳細資訊，請參閱 [set-csclientversionconfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="f7851-122">For details, see the Help topic for the [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

