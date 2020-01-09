---
title: 在商務用 Skype Server 中查看 CDR 配置資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 摘要：瞭解如何在商務用 Skype Server 中使用通話詳細資料錄製（CDR）。
ms.openlocfilehash: 976f61ac98cb02a0cd69750a581bfa5190156ff7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991678"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="94b00-103">在商務用 Skype Server 中查看 CDR 配置資訊</span><span class="sxs-lookup"><span data-stu-id="94b00-103">View CDR configuration information in Skype for Business Server</span></span>
 
<span data-ttu-id="94b00-104">**摘要：** 瞭解如何在商務用 Skype Server 中使用通話詳細資料錄製（CDR）。</span><span class="sxs-lookup"><span data-stu-id="94b00-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="94b00-105">通話詳細資料錄製（CDR）可讓您追蹤諸如對等立即訊息會話、透過網際網路通訊協定（VoIP）電話撥打電話及會議呼叫等專案的使用方式。</span><span class="sxs-lookup"><span data-stu-id="94b00-105">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="94b00-106">此使用量資料包括呼叫者、呼叫者及交談時間的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="94b00-106">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="94b00-107">當您安裝商務用 Skype Server 時，系統會為您建立單一、全域的 CDR 配置設定。</span><span class="sxs-lookup"><span data-stu-id="94b00-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="94b00-108">系統管理員也可以選擇建立可套用至個別網站的自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="94b00-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="94b00-109">您可以使用商務用 Skype Server [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) Cmdlet 來查看貴組織中使用的 CDR 設定設定。</span><span class="sxs-lookup"><span data-stu-id="94b00-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="94b00-110">使用商務用 Skype Server [控制台] 來查看 CDR 配置資訊</span><span class="sxs-lookup"><span data-stu-id="94b00-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="94b00-111">在商務用 Skype Server 的 [控制台] 中，按一下 [**監視及**封存]。</span><span class="sxs-lookup"><span data-stu-id="94b00-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="94b00-112">[**通話詳細資料記錄**] 索引標籤中會顯示所有 CDR 設定設定的清單;針對每個設定集合，您會看到集合**名稱**;是否已啟用 CDR （ **cdr**屬性）;以及是否已啟用清除（ **CDR 清除**屬性）。</span><span class="sxs-lookup"><span data-stu-id="94b00-112">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property).</span></span> <span data-ttu-id="94b00-113">若要查看集合的詳細資訊，請按兩下該集合，或選取適當的集合，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="94b00-113">To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="94b00-114">請注意，您一次只能針對單一的 CDR 配置設定集合查看詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="94b00-114">Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="94b00-115">使用 Windows PowerShell Cmdlet 來查看 CDR 配置資訊</span><span class="sxs-lookup"><span data-stu-id="94b00-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="94b00-116">您可以使用 Windows PowerShell 和 CsCdrConfiguration Cmdlet 來查看 CDR 配置設定。</span><span class="sxs-lookup"><span data-stu-id="94b00-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="94b00-117">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="94b00-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="94b00-118">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="94b00-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="94b00-119">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="94b00-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="94b00-120">若要查看 CDR 配置資訊</span><span class="sxs-lookup"><span data-stu-id="94b00-120">To view CDR configuration information</span></span>

- <span data-ttu-id="94b00-121">若要查看所有 CDR 配置設定的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="94b00-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="94b00-122">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="94b00-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="94b00-123">如需詳細資訊，請參閱[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="94b00-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

