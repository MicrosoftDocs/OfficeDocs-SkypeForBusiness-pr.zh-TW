---
title: 設定通話資料連線器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 設定呼叫資料連線器的指示, 可讓您使用商務用 Skype Online 工具查看商務用 skype 內部部署的遙測。
ms.openlocfilehash: 1851e1e0c430107a27d706f7bc16ad974c5abaed
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2019
ms.locfileid: "36185554"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="ee144-103">設定通話資料連線器</span><span class="sxs-lookup"><span data-stu-id="ee144-103">Configure Call Data Connector</span></span>

<span data-ttu-id="ee144-104">本文說明如何設定 [呼叫資料連線器]-單一工具集, 可讓您使用商務用 Skype Online 通話品質儀表板 (CQD) 和通話分析 (CA) 工具來查看商務用 Skype Server 通話品質資料。</span><span class="sxs-lookup"><span data-stu-id="ee144-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span> 

> [!NOTE]
> <span data-ttu-id="ee144-105">在公開預覽版發行時, 只有 [呼叫分析] 儀表板可供使用。</span><span class="sxs-lookup"><span data-stu-id="ee144-105">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="ee144-106">如需通話資料連線器優點與必備元件 (例如角色需求及設定混合式連線) 的詳細資訊, 請參閱[規劃通話資料連線器](plan-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="ee144-106">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="ee144-107">啟用監視</span><span class="sxs-lookup"><span data-stu-id="ee144-107">Enable Monitoring</span></span>
 
<span data-ttu-id="ee144-108">您必須在前端池監控中設定呼叫資料錄製 (CDR) 與品質 (QoE) 資料收集, 並使用本機 LCSCdr 和 QoEMetrics 資料庫;否則, [通話分析] 與 [通話品質儀表板] 不會取得資料來使用。</span><span class="sxs-lookup"><span data-stu-id="ee144-108">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="ee144-109">在您設定呼叫資料連線器之前, 請遵循在[商務用 Skype Server 中部署監視](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md)中提供的步驟, 來設定 CDR 與 QoE, 以及基本監視。</span><span class="sxs-lookup"><span data-stu-id="ee144-109">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee144-110">如果未在前端池中啟用監視, 則呼叫資料連線器將無法運作。</span><span class="sxs-lookup"><span data-stu-id="ee144-110">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="ee144-111">啟用呼叫資料連線器</span><span class="sxs-lookup"><span data-stu-id="ee144-111">Enable Call Data Connector</span></span>

<span data-ttu-id="ee144-112">若要設定及啟用呼叫資料連線器, 您將會使用下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ee144-112">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="ee144-113">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ee144-113">Cmdlet</span></span>| <span data-ttu-id="ee144-114">說明</span><span class="sxs-lookup"><span data-stu-id="ee144-114">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="ee144-115">新-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="ee144-115">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="ee144-116">建立線上資料收集器的線上 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee144-116">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="ee144-117">CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="ee144-117">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="ee144-118">可檢索現有線上資料收集器的線上 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee144-118">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="ee144-119">CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="ee144-119">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="ee144-120">可檢索由 CsCloudCallDataConnection Cmdlet 建立之連線資訊的內部部署 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee144-120">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="ee144-121">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="ee144-121">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="ee144-122">儲存由 CsCloudCallDataConnection Cmdlet 所建立之連線資訊之內部部署複本的內部部署 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee144-122">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="ee144-123">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="ee144-123">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="ee144-124">可讓您啟用或停用連接器及自訂範圍層級的內部部署 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee144-124">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="ee144-125">若要清除您的設定並重新開始, 請使用 csclouddatconnectorconfiguration Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee144-125">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="ee144-126">設定您的環境</span><span class="sxs-lookup"><span data-stu-id="ee144-126">Configure your environment</span></span> 

<span data-ttu-id="ee144-127">若要設定您的環境以啟用線上資料收集器, 您必須先以系統管理員身分登入商務用 Skype Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ee144-127">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="ee144-128">如需詳細資訊, 請參閱[使用 Office 365 PowerShell 管理商務用 Skype Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ee144-128">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="ee144-129">有兩種方法可以登入商務用 Skype Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ee144-129">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="ee144-130">從商務用 Skype Server 2019 管理命令介面 (建議的方法)</span><span class="sxs-lookup"><span data-stu-id="ee144-130">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="ee144-131">從另一個 PowerShell 會話</span><span class="sxs-lookup"><span data-stu-id="ee144-131">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="ee144-132">從商務用 Skype Server management shell 登入商務用 Skype Online PowerShell (建議的方法)</span><span class="sxs-lookup"><span data-stu-id="ee144-132">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="ee144-133">如果是第一次啟用連接器, 請執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="ee144-133">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="ee144-134">如果您收到連線已存在的錯誤, 這表示您的租使用者已存在呼叫資料連線。</span><span class="sxs-lookup"><span data-stu-id="ee144-134">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="ee144-135">在這種情況下, 請執行命令:</span><span class="sxs-lookup"><span data-stu-id="ee144-135">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="ee144-136">從另一個 PowerShell 會話登入商務用 Skype Online PowerShell (選用方法)</span><span class="sxs-lookup"><span data-stu-id="ee144-136">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="ee144-137">如果是第一次啟用連接器, 請執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="ee144-137">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="ee144-138">如果您收到連線已存在的錯誤, 這表示您的租使用者已存在呼叫資料連線。</span><span class="sxs-lookup"><span data-stu-id="ee144-138">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="ee144-139">在這種情況下, 請執行命令:</span><span class="sxs-lookup"><span data-stu-id="ee144-139">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="ee144-140">上述命令的輸出包含標記值, 在您設定內部部署環境時, 您需要按照下列步驟進行:</span><span class="sxs-lookup"><span data-stu-id="ee144-140">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="ee144-141">在商務用 Skype Server management 命令介面中, 指定下列命令:</span><span class="sxs-lookup"><span data-stu-id="ee144-141">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="ee144-142">設定範圍</span><span class="sxs-lookup"><span data-stu-id="ee144-142">Configure the scope</span></span>

<span data-ttu-id="ee144-143">您可以從商務用 Skype Server management shell 中使用 CsCloudCallDataConnectorConfiguration Cmdlet, 為特定網站或整個商務用 Skype Server 部署啟用呼叫資料連線器。</span><span class="sxs-lookup"><span data-stu-id="ee144-143">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="ee144-144">例如, 下列命令可在全域範圍內啟用呼叫資料連線器:</span><span class="sxs-lookup"><span data-stu-id="ee144-144">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="ee144-145">除了全域設定之外, 您還可以將呼叫資料連線器配置設定指派給網站範圍。</span><span class="sxs-lookup"><span data-stu-id="ee144-145">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="ee144-146">這可在監視時提供額外的管理靈活性。</span><span class="sxs-lookup"><span data-stu-id="ee144-146">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="ee144-147">例如, 管理員可以為雷德蒙的網站啟用呼叫資料連線器轉寄, 但停用都柏林網站的呼叫資料連線器轉移, 如下列範例所示:</span><span class="sxs-lookup"><span data-stu-id="ee144-147">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="ee144-148">在網站範圍設定的設定, 會優先于在全域範圍中設定的設定。</span><span class="sxs-lookup"><span data-stu-id="ee144-148">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="ee144-149">例如, 假設在全域範圍內啟用 [呼叫資料連線器轉寄], 但在網站範圍停用 (針對雷德蒙的網站)。</span><span class="sxs-lookup"><span data-stu-id="ee144-149">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="ee144-150">這表示不會針對雷德蒙者網站上的使用者轉寄通話詳細資料錄製及 QoE 資訊。</span><span class="sxs-lookup"><span data-stu-id="ee144-150">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="ee144-151">不過, 其他網站中的使用者 (也就是由全域設定所管理的使用者, 而不是雷德蒙板網站設定), 會將通話詳細資料錄製並 QoE 資訊轉寄。</span><span class="sxs-lookup"><span data-stu-id="ee144-151">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="ee144-152">[通話資料連線器] 使用的最常用設定值, 如下表所示:</span><span class="sxs-lookup"><span data-stu-id="ee144-152">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="ee144-153">Property</span><span class="sxs-lookup"><span data-stu-id="ee144-153">Property</span></span>|<span data-ttu-id="ee144-154">說明</span><span class="sxs-lookup"><span data-stu-id="ee144-154">Description</span></span>|<span data-ttu-id="ee144-155">預設值</span><span class="sxs-lookup"><span data-stu-id="ee144-155">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ee144-156">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="ee144-156">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="ee144-157">指出是否已啟用 [呼叫資料連線器]。</span><span class="sxs-lookup"><span data-stu-id="ee144-157">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="ee144-158">如果為 True, 則會將監視記錄轉寄到線上監視。</span><span class="sxs-lookup"><span data-stu-id="ee144-158">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="ee144-159">$False</span><span class="sxs-lookup"><span data-stu-id="ee144-159">$False</span></span>  <br/> |
| <span data-ttu-id="ee144-160">Identity</span><span class="sxs-lookup"><span data-stu-id="ee144-160">Identity</span></span> | <span data-ttu-id="ee144-161">決定命令的範圍階層: [全域] 或 [網站]。</span><span class="sxs-lookup"><span data-stu-id="ee144-161">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="ee144-162">化</span><span class="sxs-lookup"><span data-stu-id="ee144-162">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="ee144-163">停用通話資料連線器</span><span class="sxs-lookup"><span data-stu-id="ee144-163">Disable Call Data Connector</span></span>

<span data-ttu-id="ee144-164">停用 [呼叫資料連線器] 不會解除與 [前端] 池中的 [監視] 儲存體的關聯, 也不會卸載或以其他方式影響後端監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="ee144-164">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="ee144-165">當您停用 [呼叫資料連線器] 時, 您將無法將商務用 Skype Server 從上傳通話資料到雲端。</span><span class="sxs-lookup"><span data-stu-id="ee144-165">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="ee144-166">您可以從商務用 Skype Server management shell 中使用 CsCloudCallDataConnectorConfiguration Cmdlet 來停用呼叫資料連線器。</span><span class="sxs-lookup"><span data-stu-id="ee144-166">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="ee144-167">例如, 下列命令會透過將 EnableCallDataConnector 屬性設定為 $False 來停用全域範圍的呼叫資料連線器:</span><span class="sxs-lookup"><span data-stu-id="ee144-167">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="ee144-168">如果您想要繼續上傳通話資料至雲端, 請將 EnableCallDataConnector 屬性設回 $True, 如下列範例所示:</span><span class="sxs-lookup"><span data-stu-id="ee144-168">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="ee144-169">透過線上儀表板來查看內部部署資料</span><span class="sxs-lookup"><span data-stu-id="ee144-169">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="ee144-170">啟用 [呼叫資料連線器] 之後, 您可以在 [通話分析] 儀表板上查看您的內部部署呼叫資料, 如[使用通話分析來排查品質差的問題](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)所述。</span><span class="sxs-lookup"><span data-stu-id="ee144-170">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="ee144-171">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="ee144-171">For more information</span></span>

<span data-ttu-id="ee144-172">如需有關 Cmdlet 的詳細資訊, 您可以使用商務用 Skype Server Management Shell 中的 [取得協助] 命令。</span><span class="sxs-lookup"><span data-stu-id="ee144-172">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ee144-173">例如：</span><span class="sxs-lookup"><span data-stu-id="ee144-173">For example:</span></span>

<span data-ttu-id="ee144-174">Get-help CsCloudCallDataConnector |等</span><span class="sxs-lookup"><span data-stu-id="ee144-174">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="ee144-175">Get-help CsCloudCallDataConnector |等</span><span class="sxs-lookup"><span data-stu-id="ee144-175">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="ee144-176">Get-help CsCloudCallDataConnectorConfiguration |等</span><span class="sxs-lookup"><span data-stu-id="ee144-176">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
