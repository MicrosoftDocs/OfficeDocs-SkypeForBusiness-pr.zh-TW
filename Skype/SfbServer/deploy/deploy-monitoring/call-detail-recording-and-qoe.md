---
title: 在商務用 Skype Server 中設定通話詳細資料錄製和經驗品質設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 摘要：瞭解如何在商務用 Skype Server 中設定 CDR 及 QoE。
ms.openlocfilehash: 3e0ff3e8dab09f38d71f9b5211f900e0f0e5fe9f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790051"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="bedfa-103">在商務用 Skype Server 中設定通話詳細資料錄製和經驗品質設定</span><span class="sxs-lookup"><span data-stu-id="bedfa-103">Configure call detail recording and Quality of Experience settings in Skype for Business Server</span></span>
 
<span data-ttu-id="bedfa-104">**摘要：** 瞭解如何在商務用 Skype Server 中設定 CDR 與 QoE。</span><span class="sxs-lookup"><span data-stu-id="bedfa-104">**Summary:** Learn how to configure CDR and QoE in Skype for Business Server.</span></span>
  
<span data-ttu-id="bedfa-105">使用適用于商務用 Skype Server 的 SQL Server Reporting Services 報表來設定 CDR 與 QoE 監視。</span><span class="sxs-lookup"><span data-stu-id="bedfa-105">Configure CDR and QoE monitoring using SQL Server Reporting Services reports for Skype for Business Server.</span></span>
  
## <a name="configure-cdr-and-qoe"></a><span data-ttu-id="bedfa-106">設定 CDR 與 QoE</span><span class="sxs-lookup"><span data-stu-id="bedfa-106">Configure CDR and QoE</span></span>

<span data-ttu-id="bedfa-107">在您將監視存放區與前端池關聯之後，請設定監視存放區，然後安裝和設定 SQL Server Reporting Services 及監視報告，您可以管理呼叫詳細資料錄製（CDR）及體驗品質（QoE）使用商務用 Skype Server Management 命令介面進行監控。</span><span class="sxs-lookup"><span data-stu-id="bedfa-107">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Skype for Business Server Management Shell.</span></span> <span data-ttu-id="bedfa-108">商務用 skype Server 管理命令介面 Cmdlet 可讓您針對特定網站或整個商務用 Skype Server 部署啟用及停用 CDR 及/或 QoE 監視;如此一來，您就可以使用簡單的命令完成下列作業：</span><span class="sxs-lookup"><span data-stu-id="bedfa-108">Skype for Business Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Skype for Business Server deployment; that can be done with a command as simple as this:</span></span>
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

<span data-ttu-id="bedfa-109">當您安裝商務用 Skype Server 時，您也會安裝預先定義的 [CDR] 和 [QoE] 全域設定。</span><span class="sxs-lookup"><span data-stu-id="bedfa-109">When you install Skype for Business Server, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="bedfa-110">[通話詳細資料錄製] 使用的一些常用設定的預設值如下表所示：</span><span class="sxs-lookup"><span data-stu-id="bedfa-110">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>
  
|<span data-ttu-id="bedfa-111">**Property**</span><span class="sxs-lookup"><span data-stu-id="bedfa-111">**Property**</span></span>|<span data-ttu-id="bedfa-112">**說明**</span><span class="sxs-lookup"><span data-stu-id="bedfa-112">**Description**</span></span>|<span data-ttu-id="bedfa-113">**預設值**</span><span class="sxs-lookup"><span data-stu-id="bedfa-113">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bedfa-114">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="bedfa-114">EnableCDR</span></span>  <br/> |<span data-ttu-id="bedfa-115">指出是否已啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="bedfa-115">Indicates whether or not CDR is enabled.</span></span> <span data-ttu-id="bedfa-116">如果為 True，則會收集所有 CDR 記錄，並將其寫入監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="bedfa-116">If True, all CDR records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="bedfa-117">滿足</span><span class="sxs-lookup"><span data-stu-id="bedfa-117">True</span></span>  <br/> |
|<span data-ttu-id="bedfa-118">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="bedfa-118">EnablePurging</span></span>  <br/> |<span data-ttu-id="bedfa-119">指出 CDR 記錄是否會定期從資料庫中刪除。</span><span class="sxs-lookup"><span data-stu-id="bedfa-119">Indicates whether or not CDR records will periodically be deleted from the database.</span></span> <span data-ttu-id="bedfa-120">如果為 True，則在屬性 KeepCallDetailForDays （適用于 CDR 記錄）和 KeepErrorReportForDays （針對 CDR 錯誤）指定的時段之後，將會刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="bedfa-120">If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors).</span></span> <span data-ttu-id="bedfa-121">如果是 False，則會無限期維護 CDR 記錄。</span><span class="sxs-lookup"><span data-stu-id="bedfa-121">If False, CDR records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="bedfa-122">滿足</span><span class="sxs-lookup"><span data-stu-id="bedfa-122">True</span></span>  <br/> |
|<span data-ttu-id="bedfa-123">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="bedfa-123">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="bedfa-124">指出 CDR 記錄將保留在資料庫中的天數;任何超過指定天數的記錄都會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="bedfa-124">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="bedfa-125">不過，這只會在已啟用清除的情況下發生。</span><span class="sxs-lookup"><span data-stu-id="bedfa-125">However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="bedfa-126">KeepCallDetailForDays 可以設定為1到2562天之間（大約7年）的任何整數值。</span><span class="sxs-lookup"><span data-stu-id="bedfa-126">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span>  <br/> |<span data-ttu-id="bedfa-127">60 天</span><span class="sxs-lookup"><span data-stu-id="bedfa-127">60 days</span></span>  <br/> |
|<span data-ttu-id="bedfa-128">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="bedfa-128">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="bedfa-129">指出 CDR 錯誤報表的保留天數;任何超過指定天數的報告都會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="bedfa-129">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="bedfa-130">CDR 錯誤報表是用戶端應用程式（例如商務用 Skype Server）上傳的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="bedfa-130">CDR error reports are diagnostic reports uploaded by client applications such as Skype for Business Server.</span></span>  <br/> <span data-ttu-id="bedfa-131">您可以將此屬性設定為1到2562天之間的任何整數值。</span><span class="sxs-lookup"><span data-stu-id="bedfa-131">You can set this property to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="bedfa-132">60 天</span><span class="sxs-lookup"><span data-stu-id="bedfa-132">60 days</span></span>  <br/> |
   
<span data-ttu-id="bedfa-133">同樣地，此表格會顯示所選 QoE 設定的預設值：</span><span class="sxs-lookup"><span data-stu-id="bedfa-133">Similarly, default values for selected QoE settings are shown in this table:</span></span>
  
|<span data-ttu-id="bedfa-134">**Property**</span><span class="sxs-lookup"><span data-stu-id="bedfa-134">**Property**</span></span>|<span data-ttu-id="bedfa-135">**說明**</span><span class="sxs-lookup"><span data-stu-id="bedfa-135">**Description**</span></span>|<span data-ttu-id="bedfa-136">**預設值**</span><span class="sxs-lookup"><span data-stu-id="bedfa-136">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bedfa-137">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="bedfa-137">EnableQoE</span></span>  <br/> |<span data-ttu-id="bedfa-138">指出是否已啟用 QoE 監視。</span><span class="sxs-lookup"><span data-stu-id="bedfa-138">Indicates whether or not QoE monitoring is enabled.</span></span> <span data-ttu-id="bedfa-139">如果為 True，則會收集所有 QoE 記錄並寫入監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="bedfa-139">If True, all QoE records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="bedfa-140">滿足</span><span class="sxs-lookup"><span data-stu-id="bedfa-140">True</span></span>  <br/> |
|<span data-ttu-id="bedfa-141">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="bedfa-141">EnablePurging</span></span>  <br/> |<span data-ttu-id="bedfa-142">指出 QoE 記錄是否會定期從資料庫中刪除。</span><span class="sxs-lookup"><span data-stu-id="bedfa-142">Indicates whether or not QoE records will periodically be deleted from the database.</span></span> <span data-ttu-id="bedfa-143">如果為 True，則會在 KeepQoEDataForDays 屬性指定的時段之後刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="bedfa-143">If True, records will be deleted after the time period specified by the KeepQoEDataForDays property.</span></span> <span data-ttu-id="bedfa-144">如果是 False，QoE 記錄將會無限期維護。</span><span class="sxs-lookup"><span data-stu-id="bedfa-144">If False, QoE records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="bedfa-145">滿足</span><span class="sxs-lookup"><span data-stu-id="bedfa-145">True</span></span>  <br/> |
|<span data-ttu-id="bedfa-146">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="bedfa-146">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="bedfa-147">指出 QoE 記錄將保留在資料庫中的天數;任何超過指定天數的記錄都會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="bedfa-147">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="bedfa-148">不過，這只會在已啟用清除的情況下發生。</span><span class="sxs-lookup"><span data-stu-id="bedfa-148">However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="bedfa-149">KeepCallDetailForDays 可以設定為1到2562天之間的任何整數值。</span><span class="sxs-lookup"><span data-stu-id="bedfa-149">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="bedfa-150">60 天</span><span class="sxs-lookup"><span data-stu-id="bedfa-150">60 days</span></span>  <br/> |
   
<span data-ttu-id="bedfa-151">如果您需要修改這些全域設定，您可以使用 CsCdrConfiguration 和 CsQoEConfiguration Cmdlet 來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="bedfa-151">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="bedfa-152">例如，此命令（從商務用 Skype Server Management Shell 中執行）會停用全域範圍中的 CDR 監視;這是透過將 EnableCDR 屬性設定為 False （$False）來完成：</span><span class="sxs-lookup"><span data-stu-id="bedfa-152">For example, this command (run from within the Skype for Business Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

<span data-ttu-id="bedfa-153">請注意，停用監視並不會解除與 [前端] 池的關聯，也不會卸載或以其他方式影響後端監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="bedfa-153">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="bedfa-154">當您使用商務用 Skype 伺服器管理命令介面來停用 [CDR] 或 [QoE 監視] 時，您實際所做的只是 [商務用 Skype 伺服器] 會暫時停止收集及封存監視資料。</span><span class="sxs-lookup"><span data-stu-id="bedfa-154">When you use Skype for Business Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Skype for Business Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="bedfa-155">如果您想要繼續，在這種情況下，您只需將 EnableCDR 屬性設回 True （$True），就可以開始收集及歸檔 CDR 資料：</span><span class="sxs-lookup"><span data-stu-id="bedfa-155">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

<span data-ttu-id="bedfa-156">同樣地，這個命令會停用全域範圍的 QoE 記錄清除：</span><span class="sxs-lookup"><span data-stu-id="bedfa-156">Similarly, this command disables the purging of QoE records at the global scope:</span></span>
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

<span data-ttu-id="bedfa-157">除了全域設定，還可以將 CDR 及 QoE 設定設定指派給網站範圍。</span><span class="sxs-lookup"><span data-stu-id="bedfa-157">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope.</span></span> <span data-ttu-id="bedfa-158">這在監視時提供額外的管理靈活性;例如，管理員可以為雷德蒙的網站啟用 CDR 監視，但停用用於都柏林網站的 CDR 監視。</span><span class="sxs-lookup"><span data-stu-id="bedfa-158">This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site.</span></span> <span data-ttu-id="bedfa-159">若要在網站範圍中建立新的 CDR 配置設定，請使用類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="bedfa-159">To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

<span data-ttu-id="bedfa-160">請記住，在網站範圍設定的設定會優先于在全域範圍中設定的設定。</span><span class="sxs-lookup"><span data-stu-id="bedfa-160">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="bedfa-161">例如，假設在全域範圍中啟用 CDR 監視，但在網站範圍停用（針對雷德蒙的網站）。</span><span class="sxs-lookup"><span data-stu-id="bedfa-161">For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="bedfa-162">如此一來，就不會針對雷德蒙者網站上的使用者封存通話詳細資料記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="bedfa-162">That means that call detail recording information will not be archived for users in the Redmond site.</span></span> <span data-ttu-id="bedfa-163">不過，其他網站中的使用者（也就是由全域設定所管理的使用者，而不是雷德蒙網站設定）會將通話詳細記錄資訊存檔。</span><span class="sxs-lookup"><span data-stu-id="bedfa-163">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>
  
<span data-ttu-id="bedfa-164">您可以使用如下的命令，在網站範圍建立新的 QoE 配置設定：</span><span class="sxs-lookup"><span data-stu-id="bedfa-164">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

<span data-ttu-id="bedfa-165">如需詳細資訊，請在商務用 Skype Server Management 命令介面中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="bedfa-165">For more information, type the following commands from within the Skype for Business Server Management Shell:</span></span>
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
