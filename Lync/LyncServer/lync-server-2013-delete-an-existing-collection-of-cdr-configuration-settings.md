---
title: Lync Server 2013：刪除現有 CDR 配置設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1fdfe0829f33061b9af25a6478435964545570d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="cd4cf-102">在 Lync Server 2013 中刪除現有 CDR 設定設定集合</span><span class="sxs-lookup"><span data-stu-id="cd4cf-102">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd4cf-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="cd4cf-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="cd4cf-p101">詳細通話記錄 (CDR) 讓您能夠追蹤點對點即時訊息工作階段、Voice over Internet Protocol (VoIP) 電話通話，以及會議通話之類的使用狀況。這個使用狀況資料包含有關通話者雙方身分、通話時間以及通話時間長度的資訊。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="cd4cf-106">當您安裝 Microsoft Lync Server 2013 時，系統會為您建立單一、全域的 CDR 配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="cd4cf-107">系統管理員也可以選擇建立自訂的設定集合，以套用於個別網站。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="cd4cf-108">根據設計，在網站範圍設定的設定會優先于在全域範圍設定的設定。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="cd4cf-109">如果您刪除網站範圍的設定，則會使用通用設定在該網站中管理 CDR。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-109">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="cd4cf-110">請注意，您也可以「刪除」全域設定。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-110">Note that you can also “delete” the global settings.</span></span> <span data-ttu-id="cd4cf-111">不過，全域設定實際上不會被移除。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-111">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="cd4cf-112">相反地，該集合中的所有屬性都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-112">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="cd4cf-113">例如，預設會在 CDR 設定設定的集合中啟用清除。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-113">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="cd4cf-114">假設您修改全域集合以停用清除。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-114">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="cd4cf-115">如果您稍後刪除全域設定，所有屬性都會重設為其預設值。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-115">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="cd4cf-116">在此情況下，這表示會再次啟用清除。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-116">In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="cd4cf-117">您可以使用 Lync Server 控制台或[Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) Cmdlet 來移除 CDR 設定設定。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-117">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="cd4cf-118">使用 Lync Server 控制台移除 CDR 設定設定</span><span class="sxs-lookup"><span data-stu-id="cd4cf-118">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="cd4cf-119">在 [Lync Server 控制台] 中，按一下 [**監控和**封存]。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-119">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="cd4cf-120">在 [**詳細通話記錄**] 索引標籤上，選取要移除之 CDR 設定的集合 (或集合) 。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-120">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed.</span></span> <span data-ttu-id="cd4cf-121">若要選取多個集合，請按一下第一個集合，按住 Ctrl 鍵，然後按一下 [其他集合]。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-121">To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="cd4cf-122">按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-122">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="cd4cf-123">在 [Lync Server 控制台] 對話方塊中，按一下 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-123">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cd4cf-124">使用 Windows PowerShell Cmdlet 移除 CDR 設定設定</span><span class="sxs-lookup"><span data-stu-id="cd4cf-124">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cd4cf-125">您可以使用 Windows PowerShell 和**Remove-CsCdrConfiguration** Cmdlet 來刪除詳細通話記錄設定設定。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-125">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="cd4cf-126">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cd4cf-127">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="cd4cf-128">移除指定的 CDR 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="cd4cf-128">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="cd4cf-129">此命令會移除套用至 Redmond 網站的 CDR 設定設定：</span><span class="sxs-lookup"><span data-stu-id="cd4cf-129">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="cd4cf-130">移除所有套用至網站範圍的 CDR 設定設定</span><span class="sxs-lookup"><span data-stu-id="cd4cf-130">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="cd4cf-131">此命令會移除所有套用至網站範圍的 CDR 設定設定：</span><span class="sxs-lookup"><span data-stu-id="cd4cf-131">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="cd4cf-132">移除所有停用詳細通話記錄的 CDR 設定設定</span><span class="sxs-lookup"><span data-stu-id="cd4cf-132">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="cd4cf-133">此命令會移除已停用通話詳細資料記錄的所有 CDR 設定設定：</span><span class="sxs-lookup"><span data-stu-id="cd4cf-133">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="cd4cf-134">如需詳細資訊，請參閱[Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="cd4cf-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

