---
title: 使用 Operations Management Suite (OMS) 監控 Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 閱讀本主題以瞭解如何使用 Microsoft Operations Management Suite （OMS）來監控雲端連接器版本2.1 及更新版本的部署。
ms.openlocfilehash: 1dcac3519624cef898622f915b08b24363453b84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799623"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="44528-103">使用 Operations Management Suite (OMS) 監控 Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="44528-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="44528-104">閱讀本主題以瞭解如何使用 Microsoft Operations Management Suite （OMS）來監控雲端連接器版本2.1 及更新版本的部署。</span><span class="sxs-lookup"><span data-stu-id="44528-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="44528-105">您現在可以使用 Operations Management Suite （OMS）（Microsoft 雲端 IT 管理解決方案）來監視雲端連接器版本2.1 及更新版本的部署。</span><span class="sxs-lookup"><span data-stu-id="44528-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="44528-106">OMS 記錄分析可讓您監視及分析資源的可用性與效能，包括物理電腦和虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="44528-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="44528-107">如需 OMS 和 Log Analytics 的詳細資訊，請參閱[什麼是作業管理套件（OMS）？](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)。</span><span class="sxs-lookup"><span data-stu-id="44528-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span>

<span data-ttu-id="44528-108">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="44528-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="44528-109">先決條件</span><span class="sxs-lookup"><span data-stu-id="44528-109">Prerequisites</span></span>

- <span data-ttu-id="44528-110">將雲端連接器設定為使用 OMS</span><span class="sxs-lookup"><span data-stu-id="44528-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="44528-111">設定 OMS</span><span class="sxs-lookup"><span data-stu-id="44528-111">Configure OMS</span></span>

- <span data-ttu-id="44528-112">分析 Log Analytics 儲存庫中的警示</span><span class="sxs-lookup"><span data-stu-id="44528-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="44528-113">建議的監視設定</span><span class="sxs-lookup"><span data-stu-id="44528-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44528-114">先決條件</span><span class="sxs-lookup"><span data-stu-id="44528-114">Prerequisites</span></span>

<span data-ttu-id="44528-115">您必須先進行下列作業，才能使用 OMS 來監視雲端連接器部署：</span><span class="sxs-lookup"><span data-stu-id="44528-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="44528-116">**Azure 帳戶和 OMS 工作區。**</span><span class="sxs-lookup"><span data-stu-id="44528-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="44528-117">如果您還沒有 Azure 帳戶，您將需要建立一個，才能使用 OMS 記錄分析。</span><span class="sxs-lookup"><span data-stu-id="44528-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="44528-118">如需如何建立 Azure 帳戶並設定 OMS 工作區的相關資訊，請參閱[開始使用 Log Analytics 工作區](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)。</span><span class="sxs-lookup"><span data-stu-id="44528-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="44528-119">**雲端連接器版本2.1 或更新版本**</span><span class="sxs-lookup"><span data-stu-id="44528-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="44528-120">需要進行記錄分析的是雲端連接器監視所需的**新記錄搜尋**。</span><span class="sxs-lookup"><span data-stu-id="44528-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="44528-121">如需詳細資訊，請參閱[將您的 Azure Log Analytics 工作區升級至新的記錄搜尋](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)。</span><span class="sxs-lookup"><span data-stu-id="44528-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="44528-122">將雲端連接器設定為使用 OMS</span><span class="sxs-lookup"><span data-stu-id="44528-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="44528-123">您必須將雲端連接器內部部署環境設定為使用 OMS。</span><span class="sxs-lookup"><span data-stu-id="44528-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="44528-124">若要這麼做，您需要您的 OMS 工作區識別碼和金鑰，您可以使用 OMS 入口網站來尋找這些專案，如下所\>示： [設定\> ]-[連線的來源]-[Windows 伺服器]：</span><span class="sxs-lookup"><span data-stu-id="44528-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![雲端連接器 OMS 的螢幕擷取畫面](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="44528-126">如何將雲端連接器設定為使用 OMS，取決於您的案例：</span><span class="sxs-lookup"><span data-stu-id="44528-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="44528-127">**如果您要安裝新的雲端連接器裝置，或想要重新部署裝置**，請在執行安裝程式前按照下列步驟進行： CcAppliance：</span><span class="sxs-lookup"><span data-stu-id="44528-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

1. <span data-ttu-id="44528-128">在 CloudConnector 檔案 [Common] （通用）區段中，將 OMSEnabled 參數設定為 True。</span><span class="sxs-lookup"><span data-stu-id="44528-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

    <span data-ttu-id="44528-129">每次部署或升級雲端連接器時，都會嘗試將 OMS 代理程式自動安裝到 Vm。</span><span class="sxs-lookup"><span data-stu-id="44528-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="44528-130">啟用這項功能，以讓 OMS 代理程式可在雲端連接器自動更新後繼續進行。</span><span class="sxs-lookup"><span data-stu-id="44528-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

2. <span data-ttu-id="44528-131">若要設定 OMS 識別碼和金鑰，請執行 CcCredential-AccountType OMSWorkspace。</span><span class="sxs-lookup"><span data-stu-id="44528-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="44528-132">**如果您要在現有的雲端連接器裝置上安裝 OMS 代理程式**，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="44528-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

1. <span data-ttu-id="44528-133">在 CloudConnector 檔案 [Common] （通用）區段中，設定 OMSEnabled = true。</span><span class="sxs-lookup"><span data-stu-id="44528-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

2. <span data-ttu-id="44528-134">執行匯入-CcConfiguration。</span><span class="sxs-lookup"><span data-stu-id="44528-134">Run Import-CcConfiguration.</span></span> 

3. <span data-ttu-id="44528-135">執行安裝-CcOMSAgent。</span><span class="sxs-lookup"><span data-stu-id="44528-135">Run Install-CcOMSAgent.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="44528-136">如果您還沒有設定 OMSWorkspace 認證，當您執行安裝-CcOMSAgent 時，系統會提示您輸入認證。</span><span class="sxs-lookup"><span data-stu-id="44528-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="44528-137">**如果您想要在已安裝 OMS 代理程式的雲端連接器裝置中更新 OMS 工作區識別碼或金鑰：**</span><span class="sxs-lookup"><span data-stu-id="44528-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

1. <span data-ttu-id="44528-138">若要設定 OMS 識別碼和金鑰，請執行 CcCredential-AccountType OMSWorkspace。</span><span class="sxs-lookup"><span data-stu-id="44528-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

2. <span data-ttu-id="44528-139">若要套用更新，請執行安裝-CcOMSAgent。</span><span class="sxs-lookup"><span data-stu-id="44528-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="44528-140">**針對所有案例，請確認 agent 已連線，如下所示：**</span><span class="sxs-lookup"><span data-stu-id="44528-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="44528-141">在 OMS 入口網站中，移至 [\>設定-連線\>的來源-Windows 伺服器]。</span><span class="sxs-lookup"><span data-stu-id="44528-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="44528-142">您會看到一份已連接的電腦清單。</span><span class="sxs-lookup"><span data-stu-id="44528-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="44528-143">設定 OMS</span><span class="sxs-lookup"><span data-stu-id="44528-143">Configure OMS</span></span>

<span data-ttu-id="44528-144">接下來，您將需要使用 OMS 入口網站來指定您的 OMS 配置。</span><span class="sxs-lookup"><span data-stu-id="44528-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="44528-145">具體說來，您將需要：</span><span class="sxs-lookup"><span data-stu-id="44528-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="44528-146">指定事件記錄和效能計數器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="44528-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="44528-147">建立提醒。</span><span class="sxs-lookup"><span data-stu-id="44528-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="44528-148">指定事件記錄和效能計數器的相關資訊</span><span class="sxs-lookup"><span data-stu-id="44528-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="44528-149">在 OMS 入口網站中，您必須指定事件記錄和效能計數器的相關資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="44528-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="44528-150">移至 [設定\>]-\>[資料-資料-Windows 事件記錄]，並為下列專案新增事件記錄：</span><span class="sxs-lookup"><span data-stu-id="44528-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="44528-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="44528-151">Lync Server</span></span>

   - <span data-ttu-id="44528-152">應用程式</span><span class="sxs-lookup"><span data-stu-id="44528-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="44528-153">您必須在文字方塊中手動輸入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="44528-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="44528-154">它不會顯示在下拉式清單中的選項。</span><span class="sxs-lookup"><span data-stu-id="44528-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="44528-155">如需詳細資訊，請參閱[Log Analytics 中的 Windows 事件記錄資料來源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="44528-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="44528-156">移至 [設定\>]-\> [資料-Windows 效能計數器]，並為下列專案新增效能計數器：</span><span class="sxs-lookup"><span data-stu-id="44528-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="44528-157">**OS 層級計數器**。</span><span class="sxs-lookup"><span data-stu-id="44528-157">**OS level counters**.</span></span> <span data-ttu-id="44528-158">您可以新增 OS 階層計數器，例如處理器使用量、記憶體使用量、網路使用量，或者您可以使用現有的解決方案（例如容量和效能）、網路效能監視器，而不需明確地新增計數器。</span><span class="sxs-lookup"><span data-stu-id="44528-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="44528-159">不論您決定如何監視它們，Microsoft 建議您監視這些 OS 計數器。</span><span class="sxs-lookup"><span data-stu-id="44528-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="44528-160">**商務用 Skype 計數器**。</span><span class="sxs-lookup"><span data-stu-id="44528-160">**Skype for Business counters**.</span></span> <span data-ttu-id="44528-161">商務用 Skype 提供大量的計數器。</span><span class="sxs-lookup"><span data-stu-id="44528-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="44528-162">您可以登入任何中繼伺服器並開啟效能監視器，以找到這些計數器。</span><span class="sxs-lookup"><span data-stu-id="44528-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="44528-163">這些計數器開頭為 "LS："。</span><span class="sxs-lookup"><span data-stu-id="44528-163">These counters start with "LS:".</span></span> <span data-ttu-id="44528-164">Microsoft 建議您至少從下列容量計數器開始，並新增感興趣的其他人：</span><span class="sxs-lookup"><span data-stu-id="44528-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="44528-165">總活動通話：</span><span class="sxs-lookup"><span data-stu-id="44528-165">Total active calls:</span></span>

   - <span data-ttu-id="44528-166">LS： MediationServer-撥入電話（_Total\- ）電流</span><span class="sxs-lookup"><span data-stu-id="44528-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

   - <span data-ttu-id="44528-167">LS： MediationServer-呼出通話（_Total\- ）電流</span><span class="sxs-lookup"><span data-stu-id="44528-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="44528-168">總活動媒體旁路通話：</span><span class="sxs-lookup"><span data-stu-id="44528-168">Total active media bypass calls:</span></span>

   - <span data-ttu-id="44528-169">LS： MediationServer-撥入通話（_Total\- ）使用中的媒體旁路通話</span><span class="sxs-lookup"><span data-stu-id="44528-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

   - <span data-ttu-id="44528-170">LS： MediationServer-呼出通話（_Total\- ）動態媒體旁路通話</span><span class="sxs-lookup"><span data-stu-id="44528-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="44528-171">您必須在文字方塊中手動輸入效能計數器。</span><span class="sxs-lookup"><span data-stu-id="44528-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="44528-172">它們不會顯示為下拉式清單中的選項。</span><span class="sxs-lookup"><span data-stu-id="44528-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="44528-173">如需詳細資訊，請參閱[Log Analytics 中的 Windows 與 Linux 效能資料來源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="44528-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="44528-174">建立提醒</span><span class="sxs-lookup"><span data-stu-id="44528-174">Create alerts</span></span>

<span data-ttu-id="44528-175">OMS 中有兩種類型的警示： [結果] 通知數和 [公制測量] 警示。</span><span class="sxs-lookup"><span data-stu-id="44528-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="44528-176">如需建立通知的詳細資訊，請參閱[在 Log Analytics 中使用警示規則](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)。</span><span class="sxs-lookup"><span data-stu-id="44528-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="44528-177">建立提醒時，請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="44528-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="44528-178">確認 [警示] 為 [結果數] 警示，這是預設的選取專案。</span><span class="sxs-lookup"><span data-stu-id="44528-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="44528-179">示範查詢需要將 [結果數] 設為 [大於 0 "。</span><span class="sxs-lookup"><span data-stu-id="44528-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="44528-180">建議您將 [時間] 視窗和 [警示頻率] 都設定為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="44528-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="44528-181">建議您不要為示範通知啟用「抑制通知」。</span><span class="sxs-lookup"><span data-stu-id="44528-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="44528-182">針對一般通知案例，Microsoft 建議您建立一組通知：一個錯誤通知和一項重設警示。</span><span class="sxs-lookup"><span data-stu-id="44528-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="44528-183">針對錯誤警報，選取嚴重等級嚴重度;針對 [重設通知]，選取 [嚴重等級資訊]。</span><span class="sxs-lookup"><span data-stu-id="44528-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="44528-184">下列各節說明如何建立範例通知。</span><span class="sxs-lookup"><span data-stu-id="44528-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="44528-185">**建立警示對：「未在轉送伺服器中執行 RTCMEDSRV」和「RTCMEDSRV 已回到轉送伺服器中」**</span><span class="sxs-lookup"><span data-stu-id="44528-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="44528-186">若要建立此通知對：</span><span class="sxs-lookup"><span data-stu-id="44528-186">To create this alert pair:</span></span>

- <span data-ttu-id="44528-187">錯誤預警的查詢如下：</span><span class="sxs-lookup"><span data-stu-id="44528-187">The query for the error alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="44528-188">查詢使用電腦*中包含 "MediationServer"* 的電腦篩選。</span><span class="sxs-lookup"><span data-stu-id="44528-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="44528-189">篩選只會選取名稱中包含字串 "MediationServer" 的電腦。</span><span class="sxs-lookup"><span data-stu-id="44528-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="44528-190">您可以將篩選取代成您自己的電腦篩選，或直接將它移除。</span><span class="sxs-lookup"><span data-stu-id="44528-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="44528-191">您可以建立不含一般運算式的複雜字串篩選。</span><span class="sxs-lookup"><span data-stu-id="44528-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="44528-192">如需詳細資訊，請參閱[字串運算子](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。</span><span class="sxs-lookup"><span data-stu-id="44528-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="44528-193">您也可以選擇使用正則運算式。</span><span class="sxs-lookup"><span data-stu-id="44528-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="44528-194">此外，您也可以透過儲存搜尋查詢，並使用該群組作為您的通知查詢中的電腦篩選，來建立電腦群組。</span><span class="sxs-lookup"><span data-stu-id="44528-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="44528-195">如需詳細資訊，請參閱[Log Analytics 記錄搜尋中的電腦群組](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)。</span><span class="sxs-lookup"><span data-stu-id="44528-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="44528-196">針對每個電腦，錯誤查詢都會取得 RTCMEDSRV 服務啟動和服務停止的最後一個事件記錄。</span><span class="sxs-lookup"><span data-stu-id="44528-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="44528-197">如果最後一個事件是服務停止事件，它會傳回一個記錄;如果最後一個事件是服務啟動事件，它將不會傳回任何內容。</span><span class="sxs-lookup"><span data-stu-id="44528-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="44528-198">簡言之，查詢會傳回 RTCMEDSRV 已停止在時間視窗中的伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="44528-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="44528-199">[重設警示] 的查詢是：</span><span class="sxs-lookup"><span data-stu-id="44528-199">The query for the reset alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="44528-200">重設查詢與錯誤查詢完全相反。</span><span class="sxs-lookup"><span data-stu-id="44528-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="44528-201">針對每個電腦，如果最後一個事件是服務啟動事件，則會傳回一個，否則返回一個如果最後一個事件是服務停止事件，它將不會傳回任何內容。</span><span class="sxs-lookup"><span data-stu-id="44528-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

  <span data-ttu-id="44528-202">**建立警示對：「在中繼伺服器中過多的併發通話」和「併發呼叫回到標準載入」**</span><span class="sxs-lookup"><span data-stu-id="44528-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="44528-203">若要建立此通知：</span><span class="sxs-lookup"><span data-stu-id="44528-203">To create this alert:</span></span>

- <span data-ttu-id="44528-204">錯誤預警的查詢如下：</span><span class="sxs-lookup"><span data-stu-id="44528-204">The query for the error alert is:</span></span>

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="44528-205">針對每個電腦，查詢會取得撥入通話和撥出通話的最後一個計數器，並加總這兩個值。</span><span class="sxs-lookup"><span data-stu-id="44528-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="44528-206">如果 sum 值超過500，則會傳回一個記錄;如果不是，它將不會返回任何內容。</span><span class="sxs-lookup"><span data-stu-id="44528-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="44528-207">簡言之，查詢會傳回時間視窗中其併發呼叫太多的伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="44528-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="44528-208">[重設警示] 的查詢是：</span><span class="sxs-lookup"><span data-stu-id="44528-208">The query for the reset alert is:</span></span>

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="44528-209">重設查詢與錯誤查詢完全相反。</span><span class="sxs-lookup"><span data-stu-id="44528-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="44528-210">針對每個電腦，查詢會取得撥入通話和撥出通話的最後一個計數器，並加總這兩個值。</span><span class="sxs-lookup"><span data-stu-id="44528-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="44528-211">如果 sum 值小於500，則會傳回一個記錄;否則不會傳回任何內容。</span><span class="sxs-lookup"><span data-stu-id="44528-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

  <span data-ttu-id="44528-212">**建立警示：「伺服器上的\> CPU 使用量90或 RTCMEDIARELAY 已停止在伺服器中」警報**</span><span class="sxs-lookup"><span data-stu-id="44528-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="44528-213">若要建立此通知，查詢是：</span><span class="sxs-lookup"><span data-stu-id="44528-213">To create this alert, the query is:</span></span>

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="44528-214">如果處理器使用量超過90% 或服務曾停止，查詢會從所有電腦取得所有的處理器使用方式計數器與服務停止事件，並傳回一個記錄。</span><span class="sxs-lookup"><span data-stu-id="44528-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="44528-215">分析 Log Analytics 儲存庫中的警示</span><span class="sxs-lookup"><span data-stu-id="44528-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="44528-216">若要在您的儲存庫中分析警示，請使用通知管理方案。</span><span class="sxs-lookup"><span data-stu-id="44528-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="44528-217">如需詳細資訊，請參閱[作業管理套件（OMS）中的警示管理解決方案](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="44528-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="44528-218">建議的最小監視設定</span><span class="sxs-lookup"><span data-stu-id="44528-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="44528-219">若要找出事件記錄和效能計數器的相關問題：</span><span class="sxs-lookup"><span data-stu-id="44528-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="44528-220">**事件記錄。**</span><span class="sxs-lookup"><span data-stu-id="44528-220">**Event logs.**</span></span> <span data-ttu-id="44528-221">針對任何問題，都應該有一個事件對，其中一組事件指示有問題，另一個則表示一切正常。</span><span class="sxs-lookup"><span data-stu-id="44528-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="44528-222">在任何指定的時間期間，都是記錄的最後一個事件，指出該時間段中是否有 amiss 的內容。</span><span class="sxs-lookup"><span data-stu-id="44528-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="44528-223">**效能計數器。**</span><span class="sxs-lookup"><span data-stu-id="44528-223">**Performance Counters.**</span></span> <span data-ttu-id="44528-224">監視的計數器應該有一個閾值。</span><span class="sxs-lookup"><span data-stu-id="44528-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="44528-225">下表列出 Microsoft 建議的 [停止] 和 [開始] 事件識別碼進行監視的服務：</span><span class="sxs-lookup"><span data-stu-id="44528-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="44528-226">服務名稱</span><span class="sxs-lookup"><span data-stu-id="44528-226">Service Name</span></span>  <br/> |<span data-ttu-id="44528-227">目標伺服器角色</span><span class="sxs-lookup"><span data-stu-id="44528-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="44528-228">停止事件識別碼</span><span class="sxs-lookup"><span data-stu-id="44528-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="44528-229">開始事件 ID</span><span class="sxs-lookup"><span data-stu-id="44528-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44528-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="44528-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="44528-231">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="44528-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="44528-232">25003</span><span class="sxs-lookup"><span data-stu-id="44528-232">25003</span></span>  <br/> |<span data-ttu-id="44528-233">25002</span><span class="sxs-lookup"><span data-stu-id="44528-233">25002</span></span>  <br/> |
|<span data-ttu-id="44528-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="44528-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="44528-235">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="44528-235">Edge Server</span></span>  <br/> |<span data-ttu-id="44528-236">12289</span><span class="sxs-lookup"><span data-stu-id="44528-236">12289</span></span>  <br/> |<span data-ttu-id="44528-237">12288</span><span class="sxs-lookup"><span data-stu-id="44528-237">12288</span></span>  <br/> |
|<span data-ttu-id="44528-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="44528-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="44528-239">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="44528-239">Edge Server</span></span>  <br/> |<span data-ttu-id="44528-240">19003</span><span class="sxs-lookup"><span data-stu-id="44528-240">19003</span></span>  <br/> |<span data-ttu-id="44528-241">19002</span><span class="sxs-lookup"><span data-stu-id="44528-241">19002</span></span>  <br/> |
|<span data-ttu-id="44528-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="44528-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="44528-243">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="44528-243">Edge Server</span></span>  <br/> |<span data-ttu-id="44528-244">22003</span><span class="sxs-lookup"><span data-stu-id="44528-244">22003</span></span>  <br/> |<span data-ttu-id="44528-245">22002</span><span class="sxs-lookup"><span data-stu-id="44528-245">22002</span></span>  <br/> |

<span data-ttu-id="44528-246">下表列出 Microsoft 建議監視的網路問題：</span><span class="sxs-lookup"><span data-stu-id="44528-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="44528-247">監視器名稱</span><span class="sxs-lookup"><span data-stu-id="44528-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="44528-248">目標伺服器角色</span><span class="sxs-lookup"><span data-stu-id="44528-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="44528-249">成功事件識別碼運算式</span><span class="sxs-lookup"><span data-stu-id="44528-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="44528-250">錯誤事件識別碼運算式</span><span class="sxs-lookup"><span data-stu-id="44528-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="44528-251">失敗範例</span><span class="sxs-lookup"><span data-stu-id="44528-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="44528-252">中繼伺服器到閘道連線失敗</span><span class="sxs-lookup"><span data-stu-id="44528-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="44528-253">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="44528-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="44528-254">25062</span><span class="sxs-lookup"><span data-stu-id="44528-254">25062</span></span>                              |                                  | <span data-ttu-id="44528-255">25002</span><span class="sxs-lookup"><span data-stu-id="44528-255">25002</span></span>  <br/>           |
| <span data-ttu-id="44528-256">中繼伺服器到閘道的呼叫完成失敗</span><span class="sxs-lookup"><span data-stu-id="44528-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="44528-257">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="44528-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="44528-258">25064</span><span class="sxs-lookup"><span data-stu-id="44528-258">25064</span></span>                              |                                  | <span data-ttu-id="44528-259">25002</span><span class="sxs-lookup"><span data-stu-id="44528-259">25002</span></span>  <br/>           |
| <span data-ttu-id="44528-260">重要的網路問題</span><span class="sxs-lookup"><span data-stu-id="44528-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="44528-261">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="44528-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="44528-262">14353</span><span class="sxs-lookup"><span data-stu-id="44528-262">14353</span></span>                              |                                  | <span data-ttu-id="44528-263">12288</span><span class="sxs-lookup"><span data-stu-id="44528-263">12288</span></span>  <br/>           |

<span data-ttu-id="44528-264">下列清單列出應監視的通話容量計數器。</span><span class="sxs-lookup"><span data-stu-id="44528-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="44528-265">對於雲端連接器標準版，這些數位應該少於 500;低於雲端連接器最小版本的50。</span><span class="sxs-lookup"><span data-stu-id="44528-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="44528-266">LS： MediationServer-撥入電話（_Total\- ）電流</span><span class="sxs-lookup"><span data-stu-id="44528-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="44528-267">LS： MediationServer-呼出通話（_Total\- ）電流</span><span class="sxs-lookup"><span data-stu-id="44528-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="44528-268">LS： MediationServer-撥入通話（_Total\- ）使用中的媒體旁路通話</span><span class="sxs-lookup"><span data-stu-id="44528-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="44528-269">LS： MediationServer-呼出通話（_Total\- ）動態媒體旁路通話</span><span class="sxs-lookup"><span data-stu-id="44528-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="44528-270">另請參閱</span><span class="sxs-lookup"><span data-stu-id="44528-270">See also</span></span>

<span data-ttu-id="44528-271">如需使用 OMS 的詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="44528-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="44528-272">在 Log Analytics 中使用記錄搜尋來尋找資料</span><span class="sxs-lookup"><span data-stu-id="44528-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="44528-273">Azure Log Analytics 語言參考</span><span class="sxs-lookup"><span data-stu-id="44528-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="44528-274">瞭解記錄分析中的通知</span><span class="sxs-lookup"><span data-stu-id="44528-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="44528-275">將 Windows 電腦連線至 Azure 中的 Log Analytics 服務</span><span class="sxs-lookup"><span data-stu-id="44528-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


