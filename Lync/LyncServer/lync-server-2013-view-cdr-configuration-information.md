---
title: Lync Server 2013： 檢視 CDR 組態資訊
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
ms.openlocfilehash: ccf5658b49118f4053f0bd76b18273fb77f90237
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-cdr-configuration-information-in-lync-server-2013"></a><span data-ttu-id="dfa15-102">Lync Server 2013 中檢視 CDR 組態資訊</span><span class="sxs-lookup"><span data-stu-id="dfa15-102">View CDR configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfa15-103">_**上次修改主題：** 2013年-02-23_</span><span class="sxs-lookup"><span data-stu-id="dfa15-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="dfa15-p101">詳細通話記錄 (CDR) 讓您能夠追蹤點對點即時訊息工作階段、Voice over Internet Protocol (VoIP) 電話通話，以及會議通話之類的使用狀況。這個使用狀況資料包含有關通話者雙方身分、通話時間以及通話時間長度的資訊。</span><span class="sxs-lookup"><span data-stu-id="dfa15-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="dfa15-106">當您安裝 Microsoft Lync Server 2013 中，單一，為您建立的 CDR 組態設定全域集合。</span><span class="sxs-lookup"><span data-stu-id="dfa15-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="dfa15-107">系統管理員也可以選擇建立自訂的設定集合，以套用於個別網站。</span><span class="sxs-lookup"><span data-stu-id="dfa15-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="dfa15-108">您可以檢視 CDR 組態設定中使用您組織中使用 Lync Server Control Panel 或[Get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dfa15-108">You can view the CDR configuration settings in use in your organization by using Lync Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="dfa15-109">若要使用 Lync Server 控制台檢視 CDR 組態資訊</span><span class="sxs-lookup"><span data-stu-id="dfa15-109">To view CDR configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="dfa15-110">Lync Server 控制台] 中按一下 [**監控和封存**]。</span><span class="sxs-lookup"><span data-stu-id="dfa15-110">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="dfa15-p103">您所有 CDR 組態設定的清單將在 **[詳細通話記錄]** 索引標籤中顯示；在每一個設定集合中，您將會看到 **[名稱]** 集合；無論是否啟用 CDR (**CDR** 屬性)；無論是否啟用清除 (**CDR purging** 屬性)。若要檢視有關集合的詳細資訊，請在該集合按兩下滑鼠，或選取合適的集合，按一下 **[編輯]**，然後按一下 **[顯示詳細資訊]**。請記住，您一次只能檢視單一 CDR 組態設定集合的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="dfa15-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dfa15-114">使用 Windows PowerShell Cmdlet 檢視 CDR 組態資訊</span><span class="sxs-lookup"><span data-stu-id="dfa15-114">Viewing CDR Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dfa15-115">您可以使用 Windows PowerShell 和 Get-cscdrconfiguration cmdlet 檢視 CDR 組態設定。</span><span class="sxs-lookup"><span data-stu-id="dfa15-115">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="dfa15-116">從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段，您可以執行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dfa15-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dfa15-117">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="dfa15-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="dfa15-118">檢視 CDR 組態資訊</span><span class="sxs-lookup"><span data-stu-id="dfa15-118">To view CDR configuration information</span></span>

  - <span data-ttu-id="dfa15-119">若要檢視所有 CDR 組態設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令並按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="dfa15-119">To view information about all your CDR configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsCdrConfiguration
    
    <span data-ttu-id="dfa15-120">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="dfa15-120">That will return information similar to this:</span></span>
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

<span data-ttu-id="dfa15-121">如需詳細資訊，請參閱[Get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="dfa15-121">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

