---
title: Lync Server 2013：查看 CDR 設定資訊
description: Lync Server 2013：查看 CDR 設定資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 687ee05701c022e1d7ecfe2cd8be5190949c51d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551309"
---
# <a name="view-cdr-configuration-information-in-lync-server-2013"></a><span data-ttu-id="e033c-103">在 Lync Server 2013 中查看 CDR 設定資訊</span><span class="sxs-lookup"><span data-stu-id="e033c-103">View CDR configuration information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e033c-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e033c-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e033c-p101">詳細通話記錄 (CDR) 讓您能夠追蹤點對點即時訊息工作階段、Voice over Internet Protocol (VoIP) 電話通話，以及會議通話之類的使用狀況。這個使用狀況資料包含有關通話者雙方身分、通話時間以及通話時間長度的資訊。</span><span class="sxs-lookup"><span data-stu-id="e033c-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="e033c-107">當您安裝 Microsoft Lync Server 2013 時，系統會為您建立單一、全域的 CDR 配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="e033c-107">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="e033c-108">系統管理員也可以選擇建立自訂的設定集合，以套用於個別網站。</span><span class="sxs-lookup"><span data-stu-id="e033c-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="e033c-109">您可以使用 Lync Server 控制台或 [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) Cmdlet 來查看組織中所使用的 CDR 設定設定。</span><span class="sxs-lookup"><span data-stu-id="e033c-109">You can view the CDR configuration settings in use in your organization by using Lync Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="e033c-110">使用 Lync Server 控制台查看 CDR 設定資訊</span><span class="sxs-lookup"><span data-stu-id="e033c-110">To view CDR configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e033c-111">在 [Lync Server 控制台] 中，按一下 [ **監控和**封存]。</span><span class="sxs-lookup"><span data-stu-id="e033c-111">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="e033c-p103">您所有 CDR 組態設定的清單將在 **[詳細通話記錄]** 索引標籤中顯示；在每一個設定集合中，您將會看到 **[名稱]** 集合；無論是否啟用 CDR (**CDR** 屬性)；無論是否啟用清除 (**CDR purging** 屬性)。若要檢視有關集合的詳細資訊，請在該集合按兩下滑鼠，或選取合適的集合，按一下 **[編輯]**，然後按一下 **[顯示詳細資訊]**。請記住，您一次只能檢視單一 CDR 組態設定集合的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e033c-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e033c-115">使用 Windows PowerShell Cmdlet 來查看 CDR 設定資訊</span><span class="sxs-lookup"><span data-stu-id="e033c-115">Viewing CDR Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e033c-116">您可以使用 Windows PowerShell 和 Get-CsCdrConfiguration Cmdlet 來查看 CDR 設定設定。</span><span class="sxs-lookup"><span data-stu-id="e033c-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="e033c-117">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e033c-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e033c-118">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="e033c-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="e033c-119">檢視 CDR 組態資訊</span><span class="sxs-lookup"><span data-stu-id="e033c-119">To view CDR configuration information</span></span>

  - <span data-ttu-id="e033c-120">若要查看所有 CDR 設定設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="e033c-120">To view information about all your CDR configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsCdrConfiguration
    
    <span data-ttu-id="e033c-121">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="e033c-121">That will return information similar to this:</span></span>
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

<span data-ttu-id="e033c-122">如需詳細資訊，請參閱 [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="e033c-122">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

