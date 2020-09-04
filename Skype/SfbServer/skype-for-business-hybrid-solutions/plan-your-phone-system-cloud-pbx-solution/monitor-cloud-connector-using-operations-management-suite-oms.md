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
description: 閱讀此主題以瞭解如何使用 Microsoft Operations Management Suite (OMS) 來監視您的雲端連接器版本2.1 和更新版本。
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359089"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="424df-103">使用 Operations Management Suite (OMS) 監控 Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="424df-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="424df-104">雲端連接器 Edition 會于2021年7月31日和商務用 Skype Online 終止。</span><span class="sxs-lookup"><span data-stu-id="424df-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="424df-105">當您的組織升級至小組後，請瞭解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。</span><span class="sxs-lookup"><span data-stu-id="424df-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="424df-106">閱讀此主題以瞭解如何使用 Microsoft Operations Management Suite (OMS) 來監視您的雲端連接器版本2.1 和更新版本。</span><span class="sxs-lookup"><span data-stu-id="424df-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="424df-107">您現在可以使用 Operations Management Suite (OMS) Microsoft 雲端 IT 管理解決方案，監視您的雲端連接器版本2.1 和更新版本的部署。</span><span class="sxs-lookup"><span data-stu-id="424df-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="424df-108">OMS 記錄分析可讓您監視及分析資源的可用性和效能（包括實體和虛擬機器）。</span><span class="sxs-lookup"><span data-stu-id="424df-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="424df-109">如需 OMS 和記錄分析的詳細資訊，請參閱 [什麼是 Operations Management Suite (OMS) ？](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="424df-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="424df-110">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="424df-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="424df-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="424df-111">Prerequisites</span></span>

- <span data-ttu-id="424df-112">設定 Cloud Connector 以使用 OMS</span><span class="sxs-lookup"><span data-stu-id="424df-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="424df-113">設定 OMS</span><span class="sxs-lookup"><span data-stu-id="424df-113">Configure OMS</span></span>

- <span data-ttu-id="424df-114">分析 Log Analytics 存放庫中的警示</span><span class="sxs-lookup"><span data-stu-id="424df-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="424df-115">建議的監控集</span><span class="sxs-lookup"><span data-stu-id="424df-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="424df-116">必要條件</span><span class="sxs-lookup"><span data-stu-id="424df-116">Prerequisites</span></span>

<span data-ttu-id="424df-117">您必須先具備下列各項，您才能使用 OMS 來監視您的雲端連接器部署：</span><span class="sxs-lookup"><span data-stu-id="424df-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="424df-118">**Azure 帳戶和 OMS 工作區。**</span><span class="sxs-lookup"><span data-stu-id="424df-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="424df-119">如果您尚無 Azure 帳戶，您必須建立一個，以使用 OMS 記錄分析。</span><span class="sxs-lookup"><span data-stu-id="424df-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="424df-120">如需如何建立 Azure 帳戶及設定 OMS 工作區的詳細資訊，請參閱 [開始使用 Log Analytics 工作區](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)。</span><span class="sxs-lookup"><span data-stu-id="424df-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="424df-121">**雲端連接器版本2.1 或更新版本**</span><span class="sxs-lookup"><span data-stu-id="424df-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="424df-122">需要記錄分析-雲端連接器監控需要**新的記錄搜尋**。</span><span class="sxs-lookup"><span data-stu-id="424df-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="424df-123">如需詳細資訊，請參閱 [Upgrade a Azure Log Analytics workspace to new Log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)。</span><span class="sxs-lookup"><span data-stu-id="424df-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="424df-124">設定 Cloud Connector 以使用 OMS</span><span class="sxs-lookup"><span data-stu-id="424df-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="424df-125">您必須將雲端連接器內部部署環境設定為使用 OMS。</span><span class="sxs-lookup"><span data-stu-id="424df-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="424df-126">若要這麼做，您將需要 OMS 工作區識別碼和金鑰，您可以使用 OMS 入口網站，如下所示：設定-- \> 連線的來源-- \> Windows server：</span><span class="sxs-lookup"><span data-stu-id="424df-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![雲端連接器 OMS 的螢幕擷取畫面](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="424df-128">如何設定 Cloud Connector 以使用 OMS 取決於您的案例：</span><span class="sxs-lookup"><span data-stu-id="424df-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="424df-129">若要**安裝新的雲端連接器裝置，或想要重新部署裝置**，請在執行 CcAppliance 之前，先遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="424df-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="424df-130">在 [CloudConnector.ini 檔案 [通用] 區段中，將 OMSEnabled 參數設定為 True。</span><span class="sxs-lookup"><span data-stu-id="424df-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="424df-131">每次部署或升級 Cloud Connector 時，它都會嘗試將 OMS 代理程式自動安裝至 Vm。</span><span class="sxs-lookup"><span data-stu-id="424df-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="424df-132">啟用這項功能，使 OMS 代理程式可以繼續使用雲端連接器自動更新。</span><span class="sxs-lookup"><span data-stu-id="424df-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="424df-133">若要設定 OMS 識別碼和機碼，請執行 CcCredential-AccountType OMSWorkspace。</span><span class="sxs-lookup"><span data-stu-id="424df-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="424df-134">**若要在現有的雲端連接器裝置上安裝 OMS 代理程式**，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="424df-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="424df-135">在 [CloudConnector.ini 檔案 [通用] 區段中，設定 OMSEnabled = true。</span><span class="sxs-lookup"><span data-stu-id="424df-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="424df-136">執行匯入-CcConfiguration。</span><span class="sxs-lookup"><span data-stu-id="424df-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="424df-137">執行安裝-CcOMSAgent。</span><span class="sxs-lookup"><span data-stu-id="424df-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="424df-138">如果從未設定 OMSWorkspace 認證，當您執行 install-CcOMSAgent 時，系統會提示您輸入認證。</span><span class="sxs-lookup"><span data-stu-id="424df-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="424df-139">**如果您想要更新 Cloud Connector 裝置中已安裝 OMS 代理程式的 OMS 工作區識別碼或機碼，請執行下列動作：**</span><span class="sxs-lookup"><span data-stu-id="424df-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="424df-140">若要設定 OMS 識別碼和機碼，請執行 CcCredential-AccountType OMSWorkspace。</span><span class="sxs-lookup"><span data-stu-id="424df-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="424df-141">若要套用更新，請執行 CcOMSAgent 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="424df-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="424df-142">**在所有情況下，請確認代理程式已連接，如下所示：**</span><span class="sxs-lookup"><span data-stu-id="424df-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="424df-143">在 [OMS] 入口網站中，移至 [設定]-[ \> 連線的來源- \> Windows 伺服器]。</span><span class="sxs-lookup"><span data-stu-id="424df-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="424df-144">您會看到已連線的電腦清單。</span><span class="sxs-lookup"><span data-stu-id="424df-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="424df-145">設定 OMS</span><span class="sxs-lookup"><span data-stu-id="424df-145">Configure OMS</span></span>

<span data-ttu-id="424df-146">接下來，您將需要使用 OMS 入口網站指定您的 OMS 設定。</span><span class="sxs-lookup"><span data-stu-id="424df-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="424df-147">具體說來，您將需要：</span><span class="sxs-lookup"><span data-stu-id="424df-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="424df-148">指定事件記錄檔和效能計數器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="424df-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="424df-149">建立提醒。</span><span class="sxs-lookup"><span data-stu-id="424df-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="424df-150">指定事件記錄檔和效能計數器的相關資訊</span><span class="sxs-lookup"><span data-stu-id="424df-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="424df-151">在 OMS 入口網站中，您必須指定事件記錄檔和效能計數器的相關資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="424df-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="424df-152">移至 [設定]-[ \> 資料- \> Windows] 事件記錄檔，並新增下列專案的事件記錄：</span><span class="sxs-lookup"><span data-stu-id="424df-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="424df-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="424df-153">Lync Server</span></span>

   - <span data-ttu-id="424df-154">應用程式</span><span class="sxs-lookup"><span data-stu-id="424df-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="424df-155">您必須在文字方塊中手動輸入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="424df-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="424df-156">它不會出現在下拉式清單中的選項。</span><span class="sxs-lookup"><span data-stu-id="424df-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="424df-157">如需詳細資訊，請參閱 [記錄分析中的 Windows 事件記錄檔資料來源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="424df-157">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="424df-158">移至 [設定]-[ \> 資料- \> Windows 效能計數器]，然後新增下列專案的效能計數器：</span><span class="sxs-lookup"><span data-stu-id="424df-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="424df-159">**作業系統層級計數器**。</span><span class="sxs-lookup"><span data-stu-id="424df-159">**OS level counters**.</span></span> <span data-ttu-id="424df-160">您可以新增作業系統層級計數器（如處理器使用量、記憶體使用量、網路使用量），也可以使用現有的解決方案（如容量和效能）、網路效能監視器（不需要明確新增計數器）。</span><span class="sxs-lookup"><span data-stu-id="424df-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="424df-161">不論您決定如何進行監視，Microsoft 建議您監視這些作業系統計數器。</span><span class="sxs-lookup"><span data-stu-id="424df-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="424df-162">**商務用 Skype 計數器**。</span><span class="sxs-lookup"><span data-stu-id="424df-162">**Skype for Business counters**.</span></span> <span data-ttu-id="424df-163">商務用 Skype 提供許多計數器。</span><span class="sxs-lookup"><span data-stu-id="424df-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="424df-164">您可以登入任何轉送伺服器並開啟效能監視器，以找到這些計數器。</span><span class="sxs-lookup"><span data-stu-id="424df-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="424df-165">這些計數器的開頭為 "LS："。</span><span class="sxs-lookup"><span data-stu-id="424df-165">These counters start with "LS:".</span></span> <span data-ttu-id="424df-166">Microsoft 建議您至少從下列容量計數器開始，並新增其他感興趣的計數器：</span><span class="sxs-lookup"><span data-stu-id="424df-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="424df-167">主動通話總數：</span><span class="sxs-lookup"><span data-stu-id="424df-167">Total active calls:</span></span>

       - <span data-ttu-id="424df-168">LS： MediationServer 輸入呼叫 (_Total) \- 電流</span><span class="sxs-lookup"><span data-stu-id="424df-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="424df-169">LS： MediationServer 呼出通話 (_Total) \- 電流</span><span class="sxs-lookup"><span data-stu-id="424df-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="424df-170">Active media 旁路通話總數：</span><span class="sxs-lookup"><span data-stu-id="424df-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="424df-171">LS： MediationServer 輸入呼叫 (_Total) 作用中 \- 媒體旁路通話</span><span class="sxs-lookup"><span data-stu-id="424df-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="424df-172">LS： MediationServer 呼出通話 (_Total) 作用中 \- 媒體旁路通話</span><span class="sxs-lookup"><span data-stu-id="424df-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="424df-173">您必須在文字方塊中手動輸入效能計數器。</span><span class="sxs-lookup"><span data-stu-id="424df-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="424df-174">它們不會顯示為下拉式清單中的選項。</span><span class="sxs-lookup"><span data-stu-id="424df-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="424df-175">如需詳細資訊，請參閱 [記錄分析中的 Windows 和 Linux 效能資料來源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="424df-175">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="424df-176">建立提醒</span><span class="sxs-lookup"><span data-stu-id="424df-176">Create alerts</span></span>

<span data-ttu-id="424df-177">OMS 中有兩種警示類型： [結果] 警示和 [衡量度量值] 警示的數目。</span><span class="sxs-lookup"><span data-stu-id="424df-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="424df-178">如需建立提醒的詳細資訊，請參閱使用 [記錄分析中的警示規則](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)。</span><span class="sxs-lookup"><span data-stu-id="424df-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="424df-179">建立提醒時，您應該考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="424df-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="424df-180">確定警示是結果數目的警示，也就是預設的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="424df-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="424df-181">演示程式查詢需要 "results 數目" 設定為 "大於 0"。</span><span class="sxs-lookup"><span data-stu-id="424df-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="424df-182">建議您將時間視窗和警示頻率設定為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="424df-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="424df-183">建議您不要為示範提醒啟用「抑制提醒」。</span><span class="sxs-lookup"><span data-stu-id="424df-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="424df-184">針對一般警示案例，Microsoft 建議建立一對警示：一個錯誤警示和一個重設警示。</span><span class="sxs-lookup"><span data-stu-id="424df-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="424df-185">若為錯誤警示，請選取嚴重層級（重要）;若為重設警示，請選取 [嚴重性層級資訊]。</span><span class="sxs-lookup"><span data-stu-id="424df-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="424df-186">下列各節說明如何建立範例警示。</span><span class="sxs-lookup"><span data-stu-id="424df-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="424df-187">**建立警示對：「RTCMEDSRV 未在轉送伺服器中執行」和「RTCMEDSRV 會傳回轉送伺服器中的執行」**</span><span class="sxs-lookup"><span data-stu-id="424df-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="424df-188">若要建立此警示對：</span><span class="sxs-lookup"><span data-stu-id="424df-188">To create this alert pair:</span></span>

- <span data-ttu-id="424df-189">錯誤警示的查詢如下：</span><span class="sxs-lookup"><span data-stu-id="424df-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="424df-190">查詢使用電腦  *包含 "MediationServer"*  的電腦篩選。</span><span class="sxs-lookup"><span data-stu-id="424df-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="424df-191">篩選器只會選取其名稱中包含字串 "MediationServer" 的電腦。</span><span class="sxs-lookup"><span data-stu-id="424df-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="424df-192">您可以將篩選取代為您自己的電腦篩選，也可以只加以移除。</span><span class="sxs-lookup"><span data-stu-id="424df-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="424df-193">您可以建立沒有正則運算式的複雜字串篩選。</span><span class="sxs-lookup"><span data-stu-id="424df-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="424df-194">如需詳細資訊，請參閱 [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。</span><span class="sxs-lookup"><span data-stu-id="424df-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="424df-195">您也可以選擇使用正則運算式。</span><span class="sxs-lookup"><span data-stu-id="424df-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="424df-196">此外，您可以儲存搜尋查詢，並使用該群組做為提醒查詢中的電腦篩選，以建立電腦群組。</span><span class="sxs-lookup"><span data-stu-id="424df-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="424df-197">如需詳細資訊，請參閱 [Log Analytics 記錄搜尋中的電腦群組](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)。</span><span class="sxs-lookup"><span data-stu-id="424df-197">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="424df-198">在每一部電腦上，錯誤查詢都會取得 RTCMEDSRV 服務啟動和服務停止的最後一個事件記錄檔。</span><span class="sxs-lookup"><span data-stu-id="424df-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="424df-199">如果最後一個事件是服務停止事件，它會傳回一個記錄，否則會傳回一個記錄。如果最後一個事件是服務啟動事件，它會傳回 nothing。</span><span class="sxs-lookup"><span data-stu-id="424df-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="424df-200">簡而言之，查詢會傳回 RTCMEDSRV 已停止在時間範圍內的伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="424df-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="424df-201">重設警示的查詢為：</span><span class="sxs-lookup"><span data-stu-id="424df-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="424df-202">重設查詢與錯誤查詢完全相反。</span><span class="sxs-lookup"><span data-stu-id="424df-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="424df-203">在每一部電腦上，如果最後一個事件是服務啟動事件，它會傳回一個，否則會傳回一個。如果最後一個事件是服務停止事件，它會傳回 nothing。</span><span class="sxs-lookup"><span data-stu-id="424df-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="424df-204">**建立警示對：「轉送伺服器中的同時呼叫太多」和「同時來電回到正常載入」**</span><span class="sxs-lookup"><span data-stu-id="424df-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="424df-205">若要建立此警示：</span><span class="sxs-lookup"><span data-stu-id="424df-205">To create this alert:</span></span>

- <span data-ttu-id="424df-206">錯誤警示的查詢如下：</span><span class="sxs-lookup"><span data-stu-id="424df-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="424df-207">針對每一部電腦，查詢將取得輸入呼叫和撥出電話的最後一個計數器，並為這兩個值加總。</span><span class="sxs-lookup"><span data-stu-id="424df-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="424df-208">如果總和值超過500，它會傳回一部記錄。如果不是，它會傳回 nothing。</span><span class="sxs-lookup"><span data-stu-id="424df-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="424df-209">簡而言之，查詢會傳回一份清單，其中的並行呼叫在時間範圍內太多。</span><span class="sxs-lookup"><span data-stu-id="424df-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="424df-210">重設警示的查詢為：</span><span class="sxs-lookup"><span data-stu-id="424df-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="424df-211">重設查詢與錯誤查詢完全相反。</span><span class="sxs-lookup"><span data-stu-id="424df-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="424df-212">針對每一部電腦，查詢將取得輸入呼叫和撥出電話的最後一個計數器，並為這兩個值加總。</span><span class="sxs-lookup"><span data-stu-id="424df-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="424df-213">如果 sum 值小於500，它會傳回一部記錄。否則會傳回 nothing。</span><span class="sxs-lookup"><span data-stu-id="424df-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="424df-214">**建立警示：「伺服器上的 CPU 使用量 \> 90 或 RTCMEDIARELAY 已停止」警示**</span><span class="sxs-lookup"><span data-stu-id="424df-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="424df-215">若要建立此警示，請執行下列查詢：</span><span class="sxs-lookup"><span data-stu-id="424df-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="424df-216">此查詢會從所有電腦取得所有處理器使用量計數器和 service stop 事件，如果處理器使用量超過90% 或服務曾經停止，則傳回一個記錄。</span><span class="sxs-lookup"><span data-stu-id="424df-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="424df-217">分析 Log Analytics 存放庫中的警示</span><span class="sxs-lookup"><span data-stu-id="424df-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="424df-218">若要分析存放庫中的警示，請使用警示管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="424df-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="424df-219">如需詳細資訊，請參閱 [Operations Management Suite 中的警示管理解決方案 (OMS) ](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="424df-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="424df-220">建議的最小監控集</span><span class="sxs-lookup"><span data-stu-id="424df-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="424df-221">若要找出事件記錄及效能計數器的問題：</span><span class="sxs-lookup"><span data-stu-id="424df-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="424df-222">**事件記錄檔。**</span><span class="sxs-lookup"><span data-stu-id="424df-222">**Event logs.**</span></span> <span data-ttu-id="424df-223">針對任何問題，應有一對事件，其中一組事件會指出發生問題，另一組則表示一切正常。</span><span class="sxs-lookup"><span data-stu-id="424df-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="424df-224">在任何指定的時間期間，都是最後記錄的事件，它會指出該時段是否有 amiss。</span><span class="sxs-lookup"><span data-stu-id="424df-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="424df-225">**效能計數器。**</span><span class="sxs-lookup"><span data-stu-id="424df-225">**Performance Counters.**</span></span> <span data-ttu-id="424df-226">監視的計數器應有一個臨界值。</span><span class="sxs-lookup"><span data-stu-id="424df-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="424df-227">下表列出 Microsoft 建議透過列出 stop 和 start 事件 IDs 來進行監視的服務：</span><span class="sxs-lookup"><span data-stu-id="424df-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="424df-228">服務名稱</span><span class="sxs-lookup"><span data-stu-id="424df-228">Service Name</span></span>  <br/> |<span data-ttu-id="424df-229">目標伺服器角色</span><span class="sxs-lookup"><span data-stu-id="424df-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="424df-230">停止事件識別碼</span><span class="sxs-lookup"><span data-stu-id="424df-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="424df-231">開始事件識別碼</span><span class="sxs-lookup"><span data-stu-id="424df-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="424df-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="424df-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="424df-233">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="424df-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="424df-234">25003</span><span class="sxs-lookup"><span data-stu-id="424df-234">25003</span></span>  <br/> |<span data-ttu-id="424df-235">25002</span><span class="sxs-lookup"><span data-stu-id="424df-235">25002</span></span>  <br/> |
|<span data-ttu-id="424df-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="424df-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="424df-237">Edge Server</span><span class="sxs-lookup"><span data-stu-id="424df-237">Edge Server</span></span>  <br/> |<span data-ttu-id="424df-238">12289</span><span class="sxs-lookup"><span data-stu-id="424df-238">12289</span></span>  <br/> |<span data-ttu-id="424df-239">12288</span><span class="sxs-lookup"><span data-stu-id="424df-239">12288</span></span>  <br/> |
|<span data-ttu-id="424df-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="424df-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="424df-241">Edge Server</span><span class="sxs-lookup"><span data-stu-id="424df-241">Edge Server</span></span>  <br/> |<span data-ttu-id="424df-242">19003</span><span class="sxs-lookup"><span data-stu-id="424df-242">19003</span></span>  <br/> |<span data-ttu-id="424df-243">19002</span><span class="sxs-lookup"><span data-stu-id="424df-243">19002</span></span>  <br/> |
|<span data-ttu-id="424df-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="424df-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="424df-245">Edge Server</span><span class="sxs-lookup"><span data-stu-id="424df-245">Edge Server</span></span>  <br/> |<span data-ttu-id="424df-246">22003</span><span class="sxs-lookup"><span data-stu-id="424df-246">22003</span></span>  <br/> |<span data-ttu-id="424df-247">22002</span><span class="sxs-lookup"><span data-stu-id="424df-247">22002</span></span>  <br/> |

<span data-ttu-id="424df-248">下表列出 Microsoft 建議監控的網路問題：</span><span class="sxs-lookup"><span data-stu-id="424df-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="424df-249">監視器名稱</span><span class="sxs-lookup"><span data-stu-id="424df-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="424df-250">目標伺服器角色</span><span class="sxs-lookup"><span data-stu-id="424df-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="424df-251">Success 事件識別碼運算式</span><span class="sxs-lookup"><span data-stu-id="424df-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="424df-252">Error 事件識別碼運算式</span><span class="sxs-lookup"><span data-stu-id="424df-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="424df-253">失敗範例</span><span class="sxs-lookup"><span data-stu-id="424df-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="424df-254">轉送伺服器到閘道連線失敗</span><span class="sxs-lookup"><span data-stu-id="424df-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="424df-255">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="424df-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="424df-256">25062</span><span class="sxs-lookup"><span data-stu-id="424df-256">25062</span></span>                              |                                  | <span data-ttu-id="424df-257">25002</span><span class="sxs-lookup"><span data-stu-id="424df-257">25002</span></span>  <br/>           |
| <span data-ttu-id="424df-258">轉送伺服器到閘道的呼叫完成失敗</span><span class="sxs-lookup"><span data-stu-id="424df-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="424df-259">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="424df-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="424df-260">25064</span><span class="sxs-lookup"><span data-stu-id="424df-260">25064</span></span>                              |                                  | <span data-ttu-id="424df-261">25002</span><span class="sxs-lookup"><span data-stu-id="424df-261">25002</span></span>  <br/>           |
| <span data-ttu-id="424df-262">重大網路問題</span><span class="sxs-lookup"><span data-stu-id="424df-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="424df-263">Edge Server</span><span class="sxs-lookup"><span data-stu-id="424df-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="424df-264">14353</span><span class="sxs-lookup"><span data-stu-id="424df-264">14353</span></span>                              |                                  | <span data-ttu-id="424df-265">12288</span><span class="sxs-lookup"><span data-stu-id="424df-265">12288</span></span>  <br/>           |

<span data-ttu-id="424df-266">下表列出應該監控的呼叫容量計數器。</span><span class="sxs-lookup"><span data-stu-id="424df-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="424df-267">對於 Cloud Connector standard edition，這些號碼應小於500。小於50的雲端連接器最小 edition。</span><span class="sxs-lookup"><span data-stu-id="424df-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="424df-268">LS： MediationServer 輸入呼叫 (_Total) \- 電流</span><span class="sxs-lookup"><span data-stu-id="424df-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="424df-269">LS： MediationServer 呼出通話 (_Total) \- 電流</span><span class="sxs-lookup"><span data-stu-id="424df-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="424df-270">LS： MediationServer 輸入呼叫 (_Total) 作用中 \- 媒體旁路通話</span><span class="sxs-lookup"><span data-stu-id="424df-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="424df-271">LS： MediationServer 呼出通話 (_Total) 作用中 \- 媒體旁路通話</span><span class="sxs-lookup"><span data-stu-id="424df-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="424df-272">另請參閱</span><span class="sxs-lookup"><span data-stu-id="424df-272">See also</span></span>

<span data-ttu-id="424df-273">如需使用 OMS 的詳細資訊，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="424df-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="424df-274">在記錄分析中使用記錄搜尋來尋找資料</span><span class="sxs-lookup"><span data-stu-id="424df-274">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="424df-275">Azure 記錄分析語言參考</span><span class="sxs-lookup"><span data-stu-id="424df-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="424df-276">瞭解記錄分析中的警示</span><span class="sxs-lookup"><span data-stu-id="424df-276">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="424df-277">將 Windows 電腦連線到 Azure 中的 Log Analytics 服務</span><span class="sxs-lookup"><span data-stu-id="424df-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


