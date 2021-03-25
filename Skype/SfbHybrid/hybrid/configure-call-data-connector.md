---
title: 設定通話資料連接器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 設定呼叫資料連線器的指示，允許使用商務用 Skype Online 工具來查看商務用 Skype 內部部署的遙測。
ms.openlocfilehash: f78d59d02964bd826fc705bc193cae3e21b293a5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118992"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="6ea43-103">設定通話資料連接器</span><span class="sxs-lookup"><span data-stu-id="6ea43-103">Configure Call Data Connector</span></span>

<span data-ttu-id="6ea43-104">本文說明如何設定呼叫資料連線器--單一工具集，可使用商務用 Skype Online 通話品質儀表板來查看商務用 skype Server 呼叫品質資料 (CQD) 和呼叫分析 (CA) 工具。</span><span class="sxs-lookup"><span data-stu-id="6ea43-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="6ea43-105">如需通話資料連線器權益和必要條件的詳細資訊，例如角色需求和設定混合連線，請參閱 [Plan Call Data Connector](plan-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea43-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="6ea43-106">啟用監視</span><span class="sxs-lookup"><span data-stu-id="6ea43-106">Enable Monitoring</span></span>
 
<span data-ttu-id="6ea43-107">您必須設定 (CDR) 和經驗品質的呼叫資料記錄， (您的前端集區監控中 QoE) 資料收集，使用本機 LCSCdr 及 QoEMetrics 資料庫;否則，通話分析和通話品質儀表板將不會取得可使用的資料。</span><span class="sxs-lookup"><span data-stu-id="6ea43-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="6ea43-108">設定呼叫資料連線器之前，請遵循在 [商務用 Skype Server 中部署監控](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 中提供的步驟，以設定 CDR 和 QoE 以及基本監視。</span><span class="sxs-lookup"><span data-stu-id="6ea43-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ea43-109">如果前端集區上未啟用監視，則通話資料連線器將無法運作。</span><span class="sxs-lookup"><span data-stu-id="6ea43-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="6ea43-110">啟用呼叫資料連線器</span><span class="sxs-lookup"><span data-stu-id="6ea43-110">Enable Call Data Connector</span></span>

<span data-ttu-id="6ea43-111">若要設定及啟用呼叫資料連線器，您將會使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6ea43-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="6ea43-112">指令程式</span><span class="sxs-lookup"><span data-stu-id="6ea43-112">Cmdlet</span></span>| <span data-ttu-id="6ea43-113">描述</span><span class="sxs-lookup"><span data-stu-id="6ea43-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="6ea43-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="6ea43-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="6ea43-115">建立線上資料收集器的線上 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6ea43-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="6ea43-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="6ea43-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="6ea43-117">可檢索現有線上資料收集器的線上 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6ea43-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="6ea43-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="6ea43-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="6ea43-119">內部部署 Cmdlet，會檢索 New-CsCloudCallDataConnection Cmdlet 所建立的連線資訊。</span><span class="sxs-lookup"><span data-stu-id="6ea43-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="6ea43-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="6ea43-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="6ea43-121">內部部署指令程式，可儲存 New-CsCloudCallDataConnection Cmdlet 所建立之連線資訊的內部部署複本。</span><span class="sxs-lookup"><span data-stu-id="6ea43-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="6ea43-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ea43-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="6ea43-123">內部部署指令程式，可讓您啟用或停用連接器及自訂範圍層級。</span><span class="sxs-lookup"><span data-stu-id="6ea43-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="6ea43-124">若要清除您的設定並從頭開始，請使用 csclouddatconnectorconfiguration Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6ea43-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="6ea43-125">設定您的環境</span><span class="sxs-lookup"><span data-stu-id="6ea43-125">Configure your environment</span></span> 

<span data-ttu-id="6ea43-126">若要設定環境以啟用線上資料收集器，您必須先以系統管理員身分登入商務用 Skype Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6ea43-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="6ea43-127">如需詳細資訊，請參閱 [使用 Office 365 PowerShell 管理商務用 Skype Online](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6ea43-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="6ea43-128">有兩種方法可登入商務用 Skype Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6ea43-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="6ea43-129">從商務用 Skype Server 2019 管理命令介面 (建議方法) </span><span class="sxs-lookup"><span data-stu-id="6ea43-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="6ea43-130">從另一個 PowerShell 會話</span><span class="sxs-lookup"><span data-stu-id="6ea43-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="6ea43-131">從商務用 Skype Server 管理命令介面 (，登入商務用 Skype Online PowerShell 建議方法) </span><span class="sxs-lookup"><span data-stu-id="6ea43-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="6ea43-132">如果是第一次啟用連接器，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6ea43-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="6ea43-133">如果您收到連線已存在的錯誤，這表示您的租使用者的通話資料連線已存在。</span><span class="sxs-lookup"><span data-stu-id="6ea43-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="6ea43-134">在此情況下，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6ea43-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="6ea43-135">從其他 PowerShell 會話登入商務用 Skype Online PowerShell (選用方法) </span><span class="sxs-lookup"><span data-stu-id="6ea43-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="6ea43-136">如果是第一次啟用連接器，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6ea43-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="6ea43-137">如果您收到連線已存在的錯誤，這表示您的租使用者的通話資料連線已存在。</span><span class="sxs-lookup"><span data-stu-id="6ea43-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="6ea43-138">在此情況下，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6ea43-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="6ea43-139">上述命令的輸出包含 token 值，當您設定內部部署環境時，您會需要此值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6ea43-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="6ea43-140">在商務用 Skype Server 管理命令介面中，指定下列命令：</span><span class="sxs-lookup"><span data-stu-id="6ea43-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="6ea43-141">設定範圍</span><span class="sxs-lookup"><span data-stu-id="6ea43-141">Configure the scope</span></span>

<span data-ttu-id="6ea43-142">您可以在商務用 Skype Server 管理命令介面中使用 Set-CsCloudCallDataConnectorConfiguration Cmdlet，為特定網站或整個商務用 Skype Server 部署啟用呼叫資料連線器。</span><span class="sxs-lookup"><span data-stu-id="6ea43-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="6ea43-143">例如，下列命令會在全域範圍內啟用呼叫資料連線器：</span><span class="sxs-lookup"><span data-stu-id="6ea43-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="6ea43-144">除了通用設定之外，也可以將呼叫資料連線器設定設定指派給網站範圍。</span><span class="sxs-lookup"><span data-stu-id="6ea43-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="6ea43-145">這會在監視時提供額外的管理彈性。</span><span class="sxs-lookup"><span data-stu-id="6ea43-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="6ea43-146">例如，系統管理員可以為 Redmond 網站啟用呼叫資料連線器轉寄，但停用都柏林網站的呼叫資料連線器轉寄，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="6ea43-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="6ea43-147">在網站範圍設定的設定會優先于在全域範圍設定的設定。</span><span class="sxs-lookup"><span data-stu-id="6ea43-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="6ea43-148">例如，假設在全域範圍啟用呼叫資料連線器轉移，但在 Redmond 網站) 的網站範圍 (停用。</span><span class="sxs-lookup"><span data-stu-id="6ea43-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="6ea43-149">這表示不會為 Redmond 網站中的使用者轉寄詳細通話記錄及 QoE 資訊。</span><span class="sxs-lookup"><span data-stu-id="6ea43-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="6ea43-150">不過，其他網站中的使用者 (也就是說，全域設定所管理的使用者，而不是 Redmond 網站設定) 會有其詳細通話記錄及 QoE 資訊轉寄。</span><span class="sxs-lookup"><span data-stu-id="6ea43-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="6ea43-151">下表顯示「呼叫資料連線器」所使用之最常使用設定的值：</span><span class="sxs-lookup"><span data-stu-id="6ea43-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="6ea43-152">屬性	</span><span class="sxs-lookup"><span data-stu-id="6ea43-152">Property</span></span>|<span data-ttu-id="6ea43-153">描述</span><span class="sxs-lookup"><span data-stu-id="6ea43-153">Description</span></span>|<span data-ttu-id="6ea43-154">預設值</span><span class="sxs-lookup"><span data-stu-id="6ea43-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6ea43-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="6ea43-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="6ea43-156">會指出是否已啟用呼叫資料連線器。</span><span class="sxs-lookup"><span data-stu-id="6ea43-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="6ea43-157">如果為 True，則監控記錄會轉寄至線上監控。</span><span class="sxs-lookup"><span data-stu-id="6ea43-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="6ea43-158">$False</span><span class="sxs-lookup"><span data-stu-id="6ea43-158">$False</span></span>  <br/> |
| <span data-ttu-id="6ea43-159">身分識別</span><span class="sxs-lookup"><span data-stu-id="6ea43-159">Identity</span></span> | <span data-ttu-id="6ea43-160">決定命令的範圍層級：全域或網站。</span><span class="sxs-lookup"><span data-stu-id="6ea43-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="6ea43-161">全球</span><span class="sxs-lookup"><span data-stu-id="6ea43-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="6ea43-162">停用通話資料連線器</span><span class="sxs-lookup"><span data-stu-id="6ea43-162">Disable Call Data Connector</span></span>

<span data-ttu-id="6ea43-163">停用呼叫資料連線器時，不會解除與前端集區的關聯，也不會卸載，否則會影響後端監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="6ea43-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="6ea43-164">當您停用通話資料連線器時，會停止將通話資料上傳至雲端的商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="6ea43-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="6ea43-165">您可以從商務用 Skype Server 管理命令介面中，使用 Set-CsCloudCallDataConnectorConfiguration Cmdlet 來停用通話資料連線器。</span><span class="sxs-lookup"><span data-stu-id="6ea43-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="6ea43-166">例如，下列命令會透過將 EnableCallDataConnector 屬性設定為 $False，停用全域範圍的呼叫資料連線器：</span><span class="sxs-lookup"><span data-stu-id="6ea43-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="6ea43-167">如果您想要繼續將來電資料上傳至雲端，請將 EnableCallDataConnector 屬性設定回 $True，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="6ea43-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="6ea43-168">透過線上儀表板查看內部部署資料</span><span class="sxs-lookup"><span data-stu-id="6ea43-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="6ea43-169">啟用呼叫資料連線器之後，您可以在「呼叫分析儀表板」或「通話品質」儀表板上查看您的內部部署呼叫資料，如  [使用呼叫分析來疑難排解不良品質](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) ，以及 [開啟和使用 Microsoft 小組和商務用 Skype Online 的通話品質儀表板](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="6ea43-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="6ea43-170">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="6ea43-170">For more information</span></span>

<span data-ttu-id="6ea43-171">如需 Cmdlet 的詳細資訊，您可以使用來自商務用 Skype Server 管理命令介面的 Get-Help 命令。</span><span class="sxs-lookup"><span data-stu-id="6ea43-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="6ea43-172">例如：</span><span class="sxs-lookup"><span data-stu-id="6ea43-172">For example:</span></span>

<span data-ttu-id="6ea43-173">Get-Help Get-CsCloudCallDataConnector |更</span><span class="sxs-lookup"><span data-stu-id="6ea43-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="6ea43-174">Get-Help Set-CsCloudCallDataConnector |更</span><span class="sxs-lookup"><span data-stu-id="6ea43-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="6ea43-175">Get-Help Set-CsCloudCallDataConnectorConfiguration |更</span><span class="sxs-lookup"><span data-stu-id="6ea43-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>