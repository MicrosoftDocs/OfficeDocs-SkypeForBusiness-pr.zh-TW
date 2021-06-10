---
title: 使用 azure Microsoft Teams 會議室部署管理
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文討論如何使用 Azure 監視器Microsoft Teams 會議室以整合的端對端方式部署裝置管理。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7046fc0010a4337ea14854e356600ccf3428f9d0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117591"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a><span data-ttu-id="27f40-103">使用 :::no-loc text="Microsoft Teams Rooms"::: 部署管理 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="27f40-103">Deploy :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>

<span data-ttu-id="27f40-104">本文將討論如何使用 來設定及部署整合式、端對端管理 :::no-loc text="Microsoft Teams Rooms"::: 裝置 :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="27f40-104">This article discusses how to set up and deploy integrated, end-to-end management of :::no-loc text="Microsoft Teams Rooms"::: devices by using :::no-loc text="Azure Monitor":::.</span></span>

<span data-ttu-id="27f40-105">您可以設定 :::no-loc text="Log Analytics"::: 為內部 :::no-loc text="Azure Monitor"::: 提供基本遙測和通知，可協助管理 :::no-loc text="Microsoft Teams Rooms"::: 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="27f40-105">You can configure :::no-loc text="Log Analytics"::: within :::no-loc text="Azure Monitor"::: to provide basic telemetry and alerts that will help you manage :::no-loc text="Microsoft Teams Rooms"::: meeting room devices.</span></span> <span data-ttu-id="27f40-106">隨著您的管理解決方案逐漸成熟，您可能會決定部署額外的資料和管理功能，以建立更詳細的裝置可用性與績效視圖。</span><span class="sxs-lookup"><span data-stu-id="27f40-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="27f40-107">您可以遵循本指南，使用下列範例的儀表板，取得裝置可用性、應用程式和硬體健康情況，以及應用程式和作業系統版本發佈 :::no-loc text="Microsoft Teams Rooms"::: 的詳細狀態報表。</span><span class="sxs-lookup"><span data-stu-id="27f40-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and :::no-loc text="Microsoft Teams Rooms"::: application and operating system version distribution.</span></span>

<span data-ttu-id="27f40-108">![範例記錄分析視圖的螢幕擷取畫面Microsoft Teams 會議室](../media/Deploy-Azure-Monitor-1.png "範例記錄分析視圖Microsoft Teams 會議室")</span><span class="sxs-lookup"><span data-stu-id="27f40-108">![Screenshot of sample Log Analytics view for Microsoft Teams Rooms](../media/Deploy-Azure-Monitor-1.png "Sample Log Analytics view for Microsoft Teams Rooms")</span></span>

<span data-ttu-id="27f40-109">在較高層級上，您需要執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="27f40-109">At a high level, you need to perform the following tasks:</span></span>


1. [<span data-ttu-id="27f40-110">驗證 :::no-loc text="Log Analytics"::: 組組</span><span class="sxs-lookup"><span data-stu-id="27f40-110">Validate :::no-loc text="Log Analytics"::: configuration</span></span>](azure-monitor-deploy.md#validate_LogAnalytics)
2. [<span data-ttu-id="27f40-111">設定管理設定 :::no-loc text="Log Analytics"::: 的測試裝置</span><span class="sxs-lookup"><span data-stu-id="27f40-111">Configure test devices for :::no-loc text="Log Analytics"::: management setup</span></span>](azure-monitor-deploy.md#configure_test_devices)
3. [<span data-ttu-id="27f40-112">地圖自訂欄位</span><span class="sxs-lookup"><span data-stu-id="27f40-112">Map custom fields</span></span>](azure-monitor-deploy.md#Custom_fields)
4. [<span data-ttu-id="27f40-113">在 中 :::no-loc text="Microsoft Teams Rooms"::: 定義視圖 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="27f40-113">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>](azure-monitor-deploy.md#Define_Views)
5. [<span data-ttu-id="27f40-114">定義通知</span><span class="sxs-lookup"><span data-stu-id="27f40-114">Define alerts</span></span>](azure-monitor-deploy.md#Alerts)
6. [<span data-ttu-id="27f40-115">設定所有監控裝置</span><span class="sxs-lookup"><span data-stu-id="27f40-115">Configure all devices for Monitoring</span></span>](azure-monitor-deploy.md#configure_all_devices)
7. [<span data-ttu-id="27f40-116">設定其他 :::no-loc text="Azure Monitor"::: 解決方案</span><span class="sxs-lookup"><span data-stu-id="27f40-116">Configure additional :::no-loc text="Azure Monitor"::: solutions</span></span>](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="27f40-117">雖然使用最小組組，可以監控執行作業系統的電腦，但您仍然需要執行一些特定步驟，才能開始將代理程式部署到 :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: 所有 :::no-loc text="Microsoft Teams Rooms"::: 裝置。</span><span class="sxs-lookup"><span data-stu-id="27f40-117">Although with minimal configuration, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: can monitor a computer running a :::no-loc text="Windows"::: operating system, there are still some :::no-loc text="Microsoft Teams Rooms":::–specific steps that you need to take before you start deploying agents to all :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span>
> <span data-ttu-id="27f40-118">因此，我們強烈建議您以正確的循序執行所有設定步驟，以控制設定和設定。</span><span class="sxs-lookup"><span data-stu-id="27f40-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="27f40-119">最終結果的品質非常取決於初始組組的品質。</span><span class="sxs-lookup"><span data-stu-id="27f40-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-no-loc-textlog-analytics-configuration"></a><span data-ttu-id="27f40-120">驗證 :::no-loc text="Log Analytics"::: 組組</span><span class="sxs-lookup"><span data-stu-id="27f40-120">Validate :::no-loc text="Log Analytics"::: configuration</span></span>
<span data-ttu-id="27f40-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="27f40-121"><a name="validate_LogAnalytics"> </a></span></span>

<span data-ttu-id="27f40-122">您需要有工作區 :::no-loc text="Log Analytics"::: ，以開始從裝置收集 :::no-loc text="Microsoft Teams Rooms"::: 記錄。</span><span class="sxs-lookup"><span data-stu-id="27f40-122">You need to have a :::no-loc text="Log Analytics"::: workspace to start collecting logs from :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span> <span data-ttu-id="27f40-123">工作區是一個獨一無二的環境，具有自己的資料存放庫、 :::no-loc text="Log Analytics"::: 資料來源和解決方案。</span><span class="sxs-lookup"><span data-stu-id="27f40-123">A workspace is a unique :::no-loc text="Log Analytics"::: environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="27f40-124">如果您已經有現有的工作區，您可以使用它監控您的部署，或者您也可以建立專屬的工作區，以滿足 :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: 您的 :::no-loc text="Microsoft Teams Rooms"::: 監控需求。</span><span class="sxs-lookup"><span data-stu-id="27f40-124">If you already have an existing :::no-loc text="Log Analytics"::: workspace, you might use it to monitor your :::no-loc text="Microsoft Teams Rooms"::: deployment or alternatively, you can create a dedicated :::no-loc text="Log Analytics"::: workspace specific to your :::no-loc text="Microsoft Teams Rooms"::: monitoring needs.</span></span>

<span data-ttu-id="27f40-125">如果您需要建立新工作區，請遵循入口網站中建立工作區一文 :::no-loc text="Log Analytics"::: [ :::no-loc text="Log Analytics"::: 中的 :::no-loc text="Azure"::: 指示](/azure/azure-monitor/learn/quick-create-workspace)</span><span class="sxs-lookup"><span data-stu-id="27f40-125">If you need to create a new :::no-loc text="Log Analytics"::: workspace, follow the instructions in the article [Create a :::no-loc text="Log Analytics"::: workspace in the :::no-loc text="Azure"::: portal](/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="27f40-126">若要與 :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: 一起使用，您必須有使用中 :::no-loc text="Azure"::: 訂閱。</span><span class="sxs-lookup"><span data-stu-id="27f40-126">To use :::no-loc text="Log Analytics"::: with :::no-loc text="Azure Monitor":::, you need to have an active :::no-loc text="Azure"::: subscription.</span></span> <span data-ttu-id="27f40-127">如果您沒有訂閱，您可以建立免費試用訂閱 :::no-loc text="Azure"::: 做為起點。 [](https://azure.microsoft.com/free)</span><span class="sxs-lookup"><span data-stu-id="27f40-127">If you don't have an :::no-loc text="Azure"::: subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a><span data-ttu-id="27f40-128">設定 :::no-loc text="Log Analytics"::: 以 :::no-loc text="Microsoft Teams Rooms"::: 收集事件記錄</span><span class="sxs-lookup"><span data-stu-id="27f40-128">Configure :::no-loc text="Log Analytics"::: to collect :::no-loc text="Microsoft Teams Rooms"::: event logs</span></span>

<span data-ttu-id="27f40-129">:::no-loc text="Log Analytics"::: 只會從設定中指定的事件 :::no-loc text="Windows"::: 記錄中收集事件。</span><span class="sxs-lookup"><span data-stu-id="27f40-129">:::no-loc text="Log Analytics"::: only collects events from the :::no-loc text="Windows"::: event logs that are specified in the settings.</span></span> <span data-ttu-id="27f40-130">針對每一個記錄，只會收集具有所選嚴重性的事件。</span><span class="sxs-lookup"><span data-stu-id="27f40-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="27f40-131">您需要設定以 :::no-loc text="Log Analytics"::: 收集監控裝置和應用程式狀態所需的 :::no-loc text="Microsoft Teams Rooms"::: 記錄。</span><span class="sxs-lookup"><span data-stu-id="27f40-131">You need to configure :::no-loc text="Log Analytics"::: to collect the logs required to monitor :::no-loc text="Microsoft Teams Rooms"::: device and application status.</span></span> <span data-ttu-id="27f40-132">:::no-loc text="Microsoft Teams Rooms"::: 裝置會使用 **:::no-loc text="Skype Room System":::** 事件記錄。</span><span class="sxs-lookup"><span data-stu-id="27f40-132">:::no-loc text="Microsoft Teams Rooms"::: devices use the **:::no-loc text="Skype Room System":::** event log.</span></span>

<span data-ttu-id="27f40-133">若要設定 :::no-loc text="Log Analytics"::: 以收集 :::no-loc text="Microsoft Teams Rooms"::: 事件，請參閱[ :::no-loc text="Windows"::: 在 :::no-loc text="Azure Monitor"::: ](/azure/azure-monitor/platform/data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="27f40-133">To configure :::no-loc text="Log Analytics"::: to collect the :::no-loc text="Microsoft Teams Rooms"::: events, see [:::no-loc text="Windows"::: event log data sources in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="27f40-134">![事件記錄設定螢幕擷取畫面](../media/Deploy-Azure-Monitor-2.png "事件記錄設定")</span><span class="sxs-lookup"><span data-stu-id="27f40-134">![Screenshot of event log settings](../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27f40-135">設定 :::no-loc text="Windows"::: 事件記錄設定並輸入 **:::no-loc text="Skype Room System":::** 為事件記錄名稱，然後選取錯誤、**警告\*\*\*\*和資訊** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="27f40-135">Configure :::no-loc text="Windows"::: Event Log settings and enter **:::no-loc text="Skype Room System":::** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="27f40-136">設定 Azure 監控的測試裝置</span><span class="sxs-lookup"><span data-stu-id="27f40-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="27f40-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="27f40-137"><a name="configure_test_devices"> </a></span></span>

<span data-ttu-id="27f40-138">您必須做好準備， :::no-loc text="Log Analytics"::: 才能監控 :::no-loc text="Microsoft Teams Rooms"::: –相關事件。</span><span class="sxs-lookup"><span data-stu-id="27f40-138">You need to prepare :::no-loc text="Log Analytics"::: to be able to monitor :::no-loc text="Microsoft Teams Rooms":::–related events.</span></span> <span data-ttu-id="27f40-139">首先，您必須將代理程式部署到一或兩個您具有實體存取權的設備，並取得這些測試裝置會產生一些資料，並推送到 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: 工作區。</span><span class="sxs-lookup"><span data-stu-id="27f40-139">To start with, you need to deploy :::no-loc text="Microsoft Monitoring"::: agents to just one or two :::no-loc text="Microsoft Teams Rooms"::: devices that you have physical access to, and get those test devices generate some data and push it to the :::no-loc text="Log Analytics"::: workspace.</span></span>

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="27f40-140">安裝 :::no-loc text="Microsoft Monitoring"::: 代理程式以測試裝置</span><span class="sxs-lookup"><span data-stu-id="27f40-140">Install :::no-loc text="Microsoft Monitoring"::: agents to test devices</span></span>

<span data-ttu-id="27f40-141">使用電腦在 中的服務連線將代理程式部署到 :::no-loc text="Microsoft Monitoring"::: [ :::no-loc text="Windows"::: :::no-loc text="Log Analytics"::: 測試裝置 :::no-loc text="Azure"::: ](/azure/azure-monitor/platform/agent-windows)。</span><span class="sxs-lookup"><span data-stu-id="27f40-141">Deploy the :::no-loc text="Microsoft Monitoring"::: agent to the test devices by using the instructions provided in [Connect :::no-loc text="Windows"::: computers to the :::no-loc text="Log Analytics"::: service in :::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="27f40-142">本文提供有關部署代理程式的步驟、取得 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  \* **工作區識別碼** _ *__* :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: 和 _ 主鍵 \* 以將裝置連接到您的部署的指示，以及驗證代理程式與實例之間連接的步驟的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="27f40-142">This article provides detailed information about the steps for deploying :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows":::, instructions for obtaining the :::no-loc text="Log Analytics"::: ***Workspace ID** _ and the _ *_primary key_** to get :::no-loc text="Microsoft Teams Rooms"::: devices connected to your :::no-loc text="Azure Monitor"::: deployment, and steps to verify agent connectivity to :::no-loc text="Log Analytics"::: instance.</span></span>

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a><span data-ttu-id="27f40-143">產生 :::no-loc text="Microsoft Teams Rooms"::: 範例事件</span><span class="sxs-lookup"><span data-stu-id="27f40-143">Generate sample :::no-loc text="Microsoft Teams Rooms"::: events</span></span>

<span data-ttu-id="27f40-144">將代理程式部署到測試裝置後，請確認所需事件記錄資料是由 :::no-loc text="Microsoft Monitoring"::: 收集者 :::no-loc text="Azure Monitor"::: 所收集。</span><span class="sxs-lookup"><span data-stu-id="27f40-144">After the :::no-loc text="Microsoft Monitoring"::: agent is deployed onto the test devices, verify that the required event log data is collected by :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="27f40-145">安裝代理程式之後重新開機裝置，然後確認會議應用程式已啟動，以便它可以在事件記錄中 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 產生新事件。</span><span class="sxs-lookup"><span data-stu-id="27f40-145">Reboot the device after the installation of the :::no-loc text="Microsoft Monitoring"::: agent, and make sure that :::no-loc text="Microsoft Teams Rooms"::: Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="27f40-146">請登錄入口[ :::no-loc text="Microsoft Azure"::: 網站，](https://portal.azure.com)然後 :::no-loc text="Log Analytics"::: 前往並選取您的工作區。</span><span class="sxs-lookup"><span data-stu-id="27f40-146">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2.  <span data-ttu-id="27f40-147">列出裝置產生的心跳 :::no-loc text="Microsoft Teams Rooms"::: 事件：</span><span class="sxs-lookup"><span data-stu-id="27f40-147">List the heartbeat events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
    1.  <span data-ttu-id="27f40-148">選取您的工作區，然後前往 **記錄，** 然後使用查詢來取回具有 自訂欄位的心跳記錄 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="27f40-148">Select your workspace and go to **Logs** and use a query to retrieve the heartbeat records that will have the custom fields for :::no-loc text="Microsoft Teams Rooms":::.</span></span>
    2.  <span data-ttu-id="27f40-149">範例查詢： `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="27f40-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="27f40-150">請確定查詢會返回包含會議應用程式所產生事件的 :::no-loc text="Microsoft Teams Rooms"::: 記錄。</span><span class="sxs-lookup"><span data-stu-id="27f40-150">Make sure that the query returns log records that include events generated by the :::no-loc text="Microsoft Teams Rooms"::: meetings app.</span></span>

4.  <span data-ttu-id="27f40-151">產生硬體問題，並驗證所需事件是否登入 :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="27f40-151">Generate a hardware issue, and validate that the required events are logged in :::no-loc text="Azure Log Analytics":::.</span></span>
    1.  <span data-ttu-id="27f40-152">拔除測試系統上的其中一個周邊 :::no-loc text="Microsoft Teams Rooms"::: 裝置。</span><span class="sxs-lookup"><span data-stu-id="27f40-152">Unplug one of the peripheral devices on the test :::no-loc text="Microsoft Teams Rooms"::: system.</span></span> <span data-ttu-id="27f40-153">這可能是相機、喇叭、麥克風或會議室顯示器</span><span class="sxs-lookup"><span data-stu-id="27f40-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="27f40-154">請等候 10 分鐘，讓事件記錄填入 :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="27f40-154">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="27f40-155">使用查詢列出硬體錯誤事件： `Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="27f40-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="27f40-156">產生應用程式問題，並驗證記錄所需的事件。</span><span class="sxs-lookup"><span data-stu-id="27f40-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="27f40-157">修改應用程式組式，然後輸入不正確的會話初始通訊協定 (SIP) :::no-loc text="Microsoft Teams Rooms"::: 位址/密碼組。</span><span class="sxs-lookup"><span data-stu-id="27f40-157">Modify :::no-loc text="Microsoft Teams Rooms"::: application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="27f40-158">請等候 10 分鐘，讓事件記錄填入 :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="27f40-158">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="27f40-159">使用查詢列出應用程式錯誤事件： `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="27f40-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27f40-160">在自訂欄位可以配置之前，這些範例事件記錄是必填項。</span><span class="sxs-lookup"><span data-stu-id="27f40-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="27f40-161">在收集必要的事件記錄之前，請勿繼續進行下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="27f40-161">Don't proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="27f40-162">地圖自訂欄位</span><span class="sxs-lookup"><span data-stu-id="27f40-162">Map custom fields</span></span>
<span data-ttu-id="27f40-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="27f40-163"><a name="Custom_fields"> </a></span></span>

<span data-ttu-id="27f40-164">您可以使用自訂欄位從事件記錄中解壓縮特定資料。</span><span class="sxs-lookup"><span data-stu-id="27f40-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="27f40-165">您需要定義自訂欄位，稍後會用於磚、儀表板視圖和通知。</span><span class="sxs-lookup"><span data-stu-id="27f40-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="27f40-166">在開始[建立自訂欄位 :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/custom-fields)之前，請參閱中的自訂欄位，並熟悉概念。</span><span class="sxs-lookup"><span data-stu-id="27f40-166">See [Custom fields in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="27f40-167">若要從捕獲的事件記錄中解壓縮自訂欄位，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="27f40-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="27f40-168">請登錄入口[ :::no-loc text="Microsoft Azure"::: 網站，](https://portal.azure.com)然後 :::no-loc text="Log Analytics"::: 前往並選取您的工作區。</span><span class="sxs-lookup"><span data-stu-id="27f40-168">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="27f40-169">列出裝置產生的 :::no-loc text="Microsoft Teams Rooms"::: 事件：</span><span class="sxs-lookup"><span data-stu-id="27f40-169">List the events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
   1.  <span data-ttu-id="27f40-170">前往記錄 **，** 然後使用查詢來取回具有自訂欄位的記錄。</span><span class="sxs-lookup"><span data-stu-id="27f40-170">Go to **Logs** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="27f40-171">範例查詢： `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="27f40-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="27f40-172">選取其中一個記錄，選取左側的按鈕，然後啟動欄位提取精靈。</span><span class="sxs-lookup"><span data-stu-id="27f40-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>
4. <span data-ttu-id="27f40-173">強調要從 RenderedDescription 中抽選的資料，並提供欄位標題。</span><span class="sxs-lookup"><span data-stu-id="27f40-173">Highlight the data you'd like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="27f40-174">您應該使用的功能變數名稱會于資料表 1 中提供。</span><span class="sxs-lookup"><span data-stu-id="27f40-174">The field names that you should use are provided in Table 1.</span></span>
5. <span data-ttu-id="27f40-175">使用表格 *1* 中顯示的映射。</span><span class="sxs-lookup"><span data-stu-id="27f40-175">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="27f40-176">:::no-loc text="Log Analytics":::會在您定義 **\_ 新欄位** 時自動附加 CF 字串。</span><span class="sxs-lookup"><span data-stu-id="27f40-176">:::no-loc text="Log Analytics"::: will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27f40-177">請記住，所有 JSON 和 :::no-loc text="Log Analytics"::: 欄位都是區分大小寫的。</span><span class="sxs-lookup"><span data-stu-id="27f40-177">Remember that all JSON and :::no-loc text="Log Analytics"::: fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="27f40-178">請注意下表中每個自訂欄位所需的查詢。</span><span class="sxs-lookup"><span data-stu-id="27f40-178">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="27f40-179">您必須使用正確的查詢，以 :::no-loc text="Log Analytics"::: 成功解壓縮自訂域值。</span><span class="sxs-lookup"><span data-stu-id="27f40-179">You need to use the correct queries for :::no-loc text="Log Analytics"::: to successfully extract custom field values.</span></span>
> 
<span data-ttu-id="27f40-180">**表格 1**</span><span class="sxs-lookup"><span data-stu-id="27f40-180">**Table 1**</span></span>

| <span data-ttu-id="27f40-181">**JSON 欄位**</span><span class="sxs-lookup"><span data-stu-id="27f40-181">**JSON field**</span></span>                   | <span data-ttu-id="27f40-182">**:::no-loc text="Log Analytics"::: 自訂欄位**</span><span class="sxs-lookup"><span data-stu-id="27f40-182">**:::no-loc text="Log Analytics"::: custom field**</span></span> | <span data-ttu-id="27f40-183">**事件識別碼**</span><span class="sxs-lookup"><span data-stu-id="27f40-183">**Event ID**</span></span> | <span data-ttu-id="27f40-184">**要用於提取的查詢**</span><span class="sxs-lookup"><span data-stu-id="27f40-184">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="27f40-185">描述</span><span class="sxs-lookup"><span data-stu-id="27f40-185">Description</span></span>                      | <span data-ttu-id="27f40-186">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="27f40-186">SRSEventDescription</span></span>         | <span data-ttu-id="27f40-187">**2000**</span><span class="sxs-lookup"><span data-stu-id="27f40-187">**2000**</span></span>     | <span data-ttu-id="27f40-188">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-188">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="27f40-189">ResourceState</span><span class="sxs-lookup"><span data-stu-id="27f40-189">ResourceState</span></span>                    | <span data-ttu-id="27f40-190">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="27f40-190">SRSResourceState</span></span>            | <span data-ttu-id="27f40-191">**2000**</span><span class="sxs-lookup"><span data-stu-id="27f40-191">**2000**</span></span>     | <span data-ttu-id="27f40-192">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-192">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="27f40-193">OperationName</span><span class="sxs-lookup"><span data-stu-id="27f40-193">OperationName</span></span>                    | <span data-ttu-id="27f40-194">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="27f40-194">SRSOperationName</span></span>            | <span data-ttu-id="27f40-195">**2000**</span><span class="sxs-lookup"><span data-stu-id="27f40-195">**2000**</span></span>     | <span data-ttu-id="27f40-196">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-196">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="27f40-197">OperationResult</span><span class="sxs-lookup"><span data-stu-id="27f40-197">OperationResult</span></span>                  | <span data-ttu-id="27f40-198">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="27f40-198">SRSOperationResult</span></span>          | <span data-ttu-id="27f40-199">**2000**</span><span class="sxs-lookup"><span data-stu-id="27f40-199">**2000**</span></span>     | <span data-ttu-id="27f40-200">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-200">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="27f40-201">作業系統</span><span class="sxs-lookup"><span data-stu-id="27f40-201">OS</span></span>                               | <span data-ttu-id="27f40-202">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="27f40-202">SRSOSVersion</span></span>                | <span data-ttu-id="27f40-203">**2000**</span><span class="sxs-lookup"><span data-stu-id="27f40-203">**2000**</span></span>     | <span data-ttu-id="27f40-204">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-204">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="27f40-205">OSVersion</span><span class="sxs-lookup"><span data-stu-id="27f40-205">OSVersion</span></span>                        | <span data-ttu-id="27f40-206">SRSOSLongVersion</span><span class="sxs-lookup"><span data-stu-id="27f40-206">SRSOSLongVersion</span></span>            | <span data-ttu-id="27f40-207">**2000**</span><span class="sxs-lookup"><span data-stu-id="27f40-207">**2000**</span></span>     | <span data-ttu-id="27f40-208">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-208">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="27f40-209">別名</span><span class="sxs-lookup"><span data-stu-id="27f40-209">Alias</span></span>                            | <span data-ttu-id="27f40-210">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="27f40-210">SRSAlias</span></span>                    | <span data-ttu-id="27f40-211">**2000**</span><span class="sxs-lookup"><span data-stu-id="27f40-211">**2000**</span></span>     | <span data-ttu-id="27f40-212">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-212">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="27f40-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="27f40-213">DisplayName</span></span>                      | <span data-ttu-id="27f40-214">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="27f40-214">SRSDisplayName</span></span>              | <span data-ttu-id="27f40-215">**2000**</span><span class="sxs-lookup"><span data-stu-id="27f40-215">**2000**</span></span>     | <span data-ttu-id="27f40-216">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-216">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="27f40-217">AppVersion</span><span class="sxs-lookup"><span data-stu-id="27f40-217">AppVersion</span></span>                       | <span data-ttu-id="27f40-218">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="27f40-218">SRSAppVersion</span></span>               | <span data-ttu-id="27f40-219">**2000**</span><span class="sxs-lookup"><span data-stu-id="27f40-219">**2000**</span></span>     | <span data-ttu-id="27f40-220">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-220">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="27f40-221">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="27f40-221">IPv4Address</span></span>                      | <span data-ttu-id="27f40-222">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="27f40-222">SRSIPv4Address</span></span>              | <span data-ttu-id="27f40-223">**2000**</span><span class="sxs-lookup"><span data-stu-id="27f40-223">**2000**</span></span>     | <span data-ttu-id="27f40-224">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-224">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="27f40-225">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="27f40-225">IPv6Address</span></span>                      | <span data-ttu-id="27f40-226">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="27f40-226">SRSIPv6Address</span></span>              | <span data-ttu-id="27f40-227">**2000**</span><span class="sxs-lookup"><span data-stu-id="27f40-227">**2000**</span></span>     | <span data-ttu-id="27f40-228">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-228">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="27f40-229">會議麥克風狀態</span><span class="sxs-lookup"><span data-stu-id="27f40-229">Conference Microphone status</span></span>     | <span data-ttu-id="27f40-230">SRSConfMicrophoneStatus</span><span class="sxs-lookup"><span data-stu-id="27f40-230">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="27f40-231">**3001**</span><span class="sxs-lookup"><span data-stu-id="27f40-231">**3001**</span></span>     | <span data-ttu-id="27f40-232">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-232">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="27f40-233">會議演講者狀態</span><span class="sxs-lookup"><span data-stu-id="27f40-233">Conference Speaker status</span></span>        | <span data-ttu-id="27f40-234">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="27f40-234">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="27f40-235">**3001**</span><span class="sxs-lookup"><span data-stu-id="27f40-235">**3001**</span></span>     | <span data-ttu-id="27f40-236">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-236">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="27f40-237">預設演講者狀態</span><span class="sxs-lookup"><span data-stu-id="27f40-237">Default Speaker status</span></span>           | <span data-ttu-id="27f40-238">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="27f40-238">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="27f40-239">**3001**</span><span class="sxs-lookup"><span data-stu-id="27f40-239">**3001**</span></span>     | <span data-ttu-id="27f40-240">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-240">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="27f40-241">相機狀態</span><span class="sxs-lookup"><span data-stu-id="27f40-241">Camera status</span></span>                    | <span data-ttu-id="27f40-242">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="27f40-242">SRSCameraStatus</span></span>             | <span data-ttu-id="27f40-243">**3001**</span><span class="sxs-lookup"><span data-stu-id="27f40-243">**3001**</span></span>     | <span data-ttu-id="27f40-244">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-244">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="27f40-245">會議室顯示狀態前方</span><span class="sxs-lookup"><span data-stu-id="27f40-245">Front of Room Display status</span></span>     | <span data-ttu-id="27f40-246">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="27f40-246">SRSFORDStatus</span></span>               | <span data-ttu-id="27f40-247">**3001**</span><span class="sxs-lookup"><span data-stu-id="27f40-247">**3001**</span></span>     | <span data-ttu-id="27f40-248">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-248">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="27f40-249">動作感應器狀態</span><span class="sxs-lookup"><span data-stu-id="27f40-249">Motion Sensor status</span></span>             | <span data-ttu-id="27f40-250">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="27f40-250">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="27f40-251">**3001**</span><span class="sxs-lookup"><span data-stu-id="27f40-251">**3001**</span></span>     | <span data-ttu-id="27f40-252">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-252">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="27f40-253">HDMI 輸入狀態</span><span class="sxs-lookup"><span data-stu-id="27f40-253">HDMI Ingest status</span></span>               | <span data-ttu-id="27f40-254">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="27f40-254">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="27f40-255">**3001**</span><span class="sxs-lookup"><span data-stu-id="27f40-255">**3001**</span></span>     | <span data-ttu-id="27f40-256">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="27f40-256">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a><span data-ttu-id="27f40-257">在 中 :::no-loc text="Microsoft Teams Rooms"::: 定義視圖 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="27f40-257">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>
<span data-ttu-id="27f40-258"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="27f40-258"><a name="Define_Views"> </a></span></span>

<span data-ttu-id="27f40-259">收集資料並對應自訂欄位之後，您可以使用 View Designer 來開發包含各種磚的儀表板，以監控 :::no-loc text="Microsoft Teams Rooms"::: 事件。</span><span class="sxs-lookup"><span data-stu-id="27f40-259">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor :::no-loc text="Microsoft Teams Rooms"::: events.</span></span> <span data-ttu-id="27f40-260">使用 View Designer 建立下列磚。</span><span class="sxs-lookup"><span data-stu-id="27f40-260">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="27f40-261">詳細資訊，請參閱在 中使用[View Designer 建立 :::no-loc text="Log Analytics"::: 自訂視圖](/azure/azure-monitor/platform/view-designer)</span><span class="sxs-lookup"><span data-stu-id="27f40-261">For more information, see [Create custom views by using View Designer in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="27f40-262">本指南中的先前步驟應該已經完成，儀表板磚可以正常運作。</span><span class="sxs-lookup"><span data-stu-id="27f40-262">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a><span data-ttu-id="27f40-263">使用Microsoft Teams 會議室建立儀表板</span><span class="sxs-lookup"><span data-stu-id="27f40-263">Create a Microsoft Teams Rooms dashboard by using the import method</span></span>

<span data-ttu-id="27f40-264">您可以輸入儀表板 :::no-loc text="Microsoft Teams Rooms"::: 並開始快速監控您的裝置。</span><span class="sxs-lookup"><span data-stu-id="27f40-264">You can import an :::no-loc text="Microsoft Teams Rooms"::: dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="27f40-265">請執行下列步驟來輸入儀表板：</span><span class="sxs-lookup"><span data-stu-id="27f40-265">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="27f40-266">取得 [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) 儀表板檔案。</span><span class="sxs-lookup"><span data-stu-id="27f40-266">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="27f40-267">請登錄入口[ :::no-loc text="Microsoft Azure"::: 網站，](https://portal.azure.com)然後 :::no-loc text="Log Analytics"::: 前往並選取您的工作區。</span><span class="sxs-lookup"><span data-stu-id="27f40-267">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>
3.  <span data-ttu-id="27f40-268">開啟 **View Designer**。</span><span class="sxs-lookup"><span data-stu-id="27f40-268">Open **View Designer**.</span></span>
4.  <span data-ttu-id="27f40-269">選取 **[匯出**，然後選取 **SkypeRoomSystems_v2.omsview** 檔案。</span><span class="sxs-lookup"><span data-stu-id="27f40-269">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="27f40-270">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="27f40-270">Select **Save**.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a><span data-ttu-id="27f40-271">手動建立Microsoft Teams 會議室儀表板</span><span class="sxs-lookup"><span data-stu-id="27f40-271">Create a Microsoft Teams Rooms dashboard manually</span></span>

<span data-ttu-id="27f40-272">或者，您可以建立自己的儀表板，並只新增要監控的磚。</span><span class="sxs-lookup"><span data-stu-id="27f40-272">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="27f40-273">設定概觀磚</span><span class="sxs-lookup"><span data-stu-id="27f40-273">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="27f40-274">開啟 **View Designer**。</span><span class="sxs-lookup"><span data-stu-id="27f40-274">Open **View Designer**.</span></span>
2.  <span data-ttu-id="27f40-275">選取 **概觀磚**， **然後從圖庫** 選取兩個數字。</span><span class="sxs-lookup"><span data-stu-id="27f40-275">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="27f40-276">為磚命名 **:::no-loc text="Microsoft Teams Rooms":::** 。</span><span class="sxs-lookup"><span data-stu-id="27f40-276">Name the tile **:::no-loc text="Microsoft Teams Rooms":::**.</span></span>
4.  <span data-ttu-id="27f40-277">定義第 **一個磚**：</span><span class="sxs-lookup"><span data-stu-id="27f40-277">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="27f40-278">**圖例：** 上個月內至少送出一次心跳的裝置</span><span class="sxs-lookup"><span data-stu-id="27f40-278">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="27f40-279">**查詢：**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="27f40-279">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="27f40-280">定義第 **二個磚**：</span><span class="sxs-lookup"><span data-stu-id="27f40-280">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="27f40-281">**圖例：** 在上一小時內送出心跳的裝置</span><span class="sxs-lookup"><span data-stu-id="27f40-281">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="27f40-282">**查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="27f40-282">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="27f40-283">選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="27f40-283">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="27f40-284">建立顯示使用中裝置磚</span><span class="sxs-lookup"><span data-stu-id="27f40-284">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="27f40-285">選取 **查看儀表板** 以開始新增磚。</span><span class="sxs-lookup"><span data-stu-id="27f40-285">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="27f40-286">從 **圖庫&** 編號清單</span><span class="sxs-lookup"><span data-stu-id="27f40-286">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="27f40-287">定義 **一般** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-287">Define the **General** properties:</span></span><br>
    <span data-ttu-id="27f40-288">**群組標題：** 心跳狀態</span><span class="sxs-lookup"><span data-stu-id="27f40-288">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="27f40-289">**新群組：** 選擇</span><span class="sxs-lookup"><span data-stu-id="27f40-289">**New Group:** Selected</span></span>
4.  <span data-ttu-id="27f40-290">定義 **磚** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-290">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="27f40-291">**圖例：** 使用中的裝置 (過去 20 分鐘內的心跳) </span><span class="sxs-lookup"><span data-stu-id="27f40-291">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="27f40-292">**磚查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="27f40-292">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="27f40-293">定義 **清單** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-293">Define the **List** properties:</span></span><br>
    <span data-ttu-id="27f40-294">**清單查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="27f40-294">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="27f40-295">定義 **欄標題**：</span><span class="sxs-lookup"><span data-stu-id="27f40-295">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="27f40-296">**名稱：** 電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="27f40-296">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="27f40-297">**值：** 最後一個心跳</span><span class="sxs-lookup"><span data-stu-id="27f40-297">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="27f40-298">定義 **流覽查詢**。</span><span class="sxs-lookup"><span data-stu-id="27f40-298">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="27f40-299">選取 **Apply**，然後 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="27f40-299">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="27f40-300">建立顯示有連接問題的裝置磚</span><span class="sxs-lookup"><span data-stu-id="27f40-300">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="27f40-301">從 **圖庫&** 編號清單，然後新增磚。</span><span class="sxs-lookup"><span data-stu-id="27f40-301">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="27f40-302">定義 **一般** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-302">Define the **General** properties:</span></span><br>
    <span data-ttu-id="27f40-303">**群組標題：** 保留空白</span><span class="sxs-lookup"><span data-stu-id="27f40-303">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="27f40-304">**新群組：** 未選取</span><span class="sxs-lookup"><span data-stu-id="27f40-304">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="27f40-305">定義 **磚** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-305">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="27f40-306">**圖例：** 非 (裝置) </span><span class="sxs-lookup"><span data-stu-id="27f40-306">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="27f40-307">**磚查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="27f40-307">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="27f40-308">定義 **清單** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-308">Define the **List** properties:</span></span><br>
    <span data-ttu-id="27f40-309">**清單查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="27f40-309">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="27f40-310">定義 **欄標題**：</span><span class="sxs-lookup"><span data-stu-id="27f40-310">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="27f40-311">**名稱：** 電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="27f40-311">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="27f40-312">**值：** 最後一個心跳</span><span class="sxs-lookup"><span data-stu-id="27f40-312">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="27f40-313">定義 **流覽查詢**：</span><span class="sxs-lookup"><span data-stu-id="27f40-313">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="27f40-314">選取 **Apply**，然後 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="27f40-314">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="27f40-315">建立顯示硬體錯誤的裝置磚</span><span class="sxs-lookup"><span data-stu-id="27f40-315">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="27f40-316">從 **圖庫&** 編號清單，然後新增磚。</span><span class="sxs-lookup"><span data-stu-id="27f40-316">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="27f40-317">定義 **一般** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-317">Define the **General** properties:</span></span><br>
    <span data-ttu-id="27f40-318">**群組標題：** 硬體狀態</span><span class="sxs-lookup"><span data-stu-id="27f40-318">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="27f40-319">**新群組：** 選擇</span><span class="sxs-lookup"><span data-stu-id="27f40-319">**New Group:** Selected</span></span>
3.  <span data-ttu-id="27f40-320">定義 **磚** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-320">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="27f40-321">**圖例：** 過去一小時內發生硬體錯誤的裝置</span><span class="sxs-lookup"><span data-stu-id="27f40-321">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="27f40-322">**磚查詢：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="27f40-322">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="27f40-323">定義 **清單** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-323">Define the **List** properties:</span></span><br>
    <span data-ttu-id="27f40-324">**清單查詢：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="27f40-324">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="27f40-325">定義 **欄標題**：</span><span class="sxs-lookup"><span data-stu-id="27f40-325">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="27f40-326">**名稱：** 電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="27f40-326">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="27f40-327">**值：** 上次錯誤</span><span class="sxs-lookup"><span data-stu-id="27f40-327">**Value:** Last Error</span></span>
6.  <span data-ttu-id="27f40-328">定義 **流覽查詢**：</span><span class="sxs-lookup"><span data-stu-id="27f40-328">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="27f40-329">選取 **Apply**，然後 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="27f40-329">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a><span data-ttu-id="27f40-330">建立顯示作業系統 :::no-loc text="Microsoft Teams Rooms"::: 版本的磚</span><span class="sxs-lookup"><span data-stu-id="27f40-330">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: Operating System versions</span></span>

1.  <span data-ttu-id="27f40-331">從 **圖庫&** 環圈清單，然後新增磚。</span><span class="sxs-lookup"><span data-stu-id="27f40-331">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="27f40-332">定義 **一般** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-332">Define the **General** properties:</span></span><br>
    <span data-ttu-id="27f40-333">**群組標題：** 作業系統詳細資料</span><span class="sxs-lookup"><span data-stu-id="27f40-333">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="27f40-334">**新群組：** 選擇</span><span class="sxs-lookup"><span data-stu-id="27f40-334">**New Group:** Selected</span></span>
3.  <span data-ttu-id="27f40-335">定義 **標題** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-335">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="27f40-336">**標題：** 作業系統版本</span><span class="sxs-lookup"><span data-stu-id="27f40-336">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="27f40-337">**副標題：** 執行特定作業系統版本的裝置</span><span class="sxs-lookup"><span data-stu-id="27f40-337">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="27f40-338">定義 **環圈** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-338">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="27f40-339">**查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="27f40-339">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="27f40-340">**文字中央：** 設備</span><span class="sxs-lookup"><span data-stu-id="27f40-340">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="27f40-341">**作業：** 和</span><span class="sxs-lookup"><span data-stu-id="27f40-341">**Operation:** Sum</span></span>
5.  <span data-ttu-id="27f40-342">定義 **清單** 屬性。</span><span class="sxs-lookup"><span data-stu-id="27f40-342">Define the **List** properties.</span></span><br>
    <span data-ttu-id="27f40-343">**清單查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="27f40-343">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="27f40-344">**隱藏Graph：** 選擇</span><span class="sxs-lookup"><span data-stu-id="27f40-344">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="27f40-345">**啟用走勢圖：** 未選取</span><span class="sxs-lookup"><span data-stu-id="27f40-345">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="27f40-346">定義 **欄標題**。</span><span class="sxs-lookup"><span data-stu-id="27f40-346">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="27f40-347">**名稱：** 電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="27f40-347">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="27f40-348">**值：** 保留空白</span><span class="sxs-lookup"><span data-stu-id="27f40-348">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="27f40-349">定義 **流覽查詢**。</span><span class="sxs-lookup"><span data-stu-id="27f40-349">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="27f40-350">選取 **Apply，** 然後 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="27f40-350">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a><span data-ttu-id="27f40-351">建立顯示應用程式 :::no-loc text="Microsoft Teams Rooms"::: 版本的磚</span><span class="sxs-lookup"><span data-stu-id="27f40-351">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: application versions</span></span>

1.  <span data-ttu-id="27f40-352">從 **圖庫&** 環圈清單，然後新增磚。</span><span class="sxs-lookup"><span data-stu-id="27f40-352">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="27f40-353">定義 **一般** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-353">Define the **General** properties:</span></span><br>
    <span data-ttu-id="27f40-354">**群組標題：** :::no-loc text="Microsoft Teams Rooms"::: 應用程式詳細資料</span><span class="sxs-lookup"><span data-stu-id="27f40-354">**Group Title:** :::no-loc text="Microsoft Teams Rooms"::: application details</span></span><br>
    <span data-ttu-id="27f40-355">**新群組：** 選擇</span><span class="sxs-lookup"><span data-stu-id="27f40-355">**New Group:** Selected</span></span>
3.  <span data-ttu-id="27f40-356">定義 **標題** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-356">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="27f40-357">**標題：** 應用程式版本</span><span class="sxs-lookup"><span data-stu-id="27f40-357">**Title:** Application versions</span></span><br>
    <span data-ttu-id="27f40-358">**副標題：** 執行特定應用程式版本的裝置</span><span class="sxs-lookup"><span data-stu-id="27f40-358">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="27f40-359">定義 **環圈** 屬性：</span><span class="sxs-lookup"><span data-stu-id="27f40-359">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="27f40-360">**查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="27f40-360">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="27f40-361">**文字中央：** 設備</span><span class="sxs-lookup"><span data-stu-id="27f40-361">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="27f40-362">**作業：** 和</span><span class="sxs-lookup"><span data-stu-id="27f40-362">**Operation:** Sum</span></span>
5.  <span data-ttu-id="27f40-363">定義 **清單** 屬性。</span><span class="sxs-lookup"><span data-stu-id="27f40-363">Define the **List** properties.</span></span><br>
    <span data-ttu-id="27f40-364">**清單查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="27f40-364">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="27f40-365">**隱藏Graph：** 選擇</span><span class="sxs-lookup"><span data-stu-id="27f40-365">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="27f40-366">**啟用走勢圖：** 未選取</span><span class="sxs-lookup"><span data-stu-id="27f40-366">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="27f40-367">定義 **欄標題**。</span><span class="sxs-lookup"><span data-stu-id="27f40-367">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="27f40-368">**名稱：** 電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="27f40-368">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="27f40-369">**值：** 保留空白</span><span class="sxs-lookup"><span data-stu-id="27f40-369">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="27f40-370">定義 **流覽查詢**。</span><span class="sxs-lookup"><span data-stu-id="27f40-370">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="27f40-371">選取 **Apply，** 然後 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="27f40-371">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="27f40-372">建立顯示有應用程式錯誤的裝置磚</span><span class="sxs-lookup"><span data-stu-id="27f40-372">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="27f40-373">從 **圖庫&** 編號清單，然後新增磚。</span><span class="sxs-lookup"><span data-stu-id="27f40-373">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="27f40-374">定義 **一般** 屬性。</span><span class="sxs-lookup"><span data-stu-id="27f40-374">Define the **General** properties.</span></span><br>
    <span data-ttu-id="27f40-375">**群組標題：** 保留空白</span><span class="sxs-lookup"><span data-stu-id="27f40-375">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="27f40-376">**新群組：** 未選取</span><span class="sxs-lookup"><span data-stu-id="27f40-376">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="27f40-377">定義 **磚** 屬性。</span><span class="sxs-lookup"><span data-stu-id="27f40-377">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="27f40-378">**圖例：** 過去一小時內發生應用程式錯誤的裝置</span><span class="sxs-lookup"><span data-stu-id="27f40-378">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="27f40-379">**磚查詢：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="27f40-379">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="27f40-380">定義 **清單** 屬性。</span><span class="sxs-lookup"><span data-stu-id="27f40-380">Define the **List** properties.</span></span><br>
    <span data-ttu-id="27f40-381">**清單查詢：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="27f40-381">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="27f40-382">定義 **欄標題**。</span><span class="sxs-lookup"><span data-stu-id="27f40-382">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="27f40-383">**名稱：** 電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="27f40-383">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="27f40-384">**值：** 上次錯誤</span><span class="sxs-lookup"><span data-stu-id="27f40-384">**Value:** Last Error</span></span>
6.  <span data-ttu-id="27f40-385">定義 **流覽查詢**。</span><span class="sxs-lookup"><span data-stu-id="27f40-385">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="27f40-386">選取 **Apply，** 然後 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="27f40-386">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="27f40-387">建立顯示已重新開機之裝置的磚</span><span class="sxs-lookup"><span data-stu-id="27f40-387">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="27f40-388">從 **圖庫&** 編號清單，然後新增磚。</span><span class="sxs-lookup"><span data-stu-id="27f40-388">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="27f40-389">定義 **一般** 屬性。</span><span class="sxs-lookup"><span data-stu-id="27f40-389">Define the **General** properties.</span></span><br>
    <span data-ttu-id="27f40-390">**群組標題：** 保留空白</span><span class="sxs-lookup"><span data-stu-id="27f40-390">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="27f40-391">**新群組：** 未選取</span><span class="sxs-lookup"><span data-stu-id="27f40-391">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="27f40-392">定義 **磚** 屬性。</span><span class="sxs-lookup"><span data-stu-id="27f40-392">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="27f40-393">**圖例：** 過去 24 小時內重新開機應用程式的裝置，以及重新開機次數</span><span class="sxs-lookup"><span data-stu-id="27f40-393">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="27f40-394">**磚查詢：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="27f40-394">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="27f40-395">定義 **清單** 屬性。</span><span class="sxs-lookup"><span data-stu-id="27f40-395">Define the **List** properties.</span></span><br>
    <span data-ttu-id="27f40-396">**清單查詢：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="27f40-396">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="27f40-397">定義 **欄標題**。</span><span class="sxs-lookup"><span data-stu-id="27f40-397">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="27f40-398">**名稱：** 電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="27f40-398">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="27f40-399">**值：** 重新開機次數</span><span class="sxs-lookup"><span data-stu-id="27f40-399">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="27f40-400">定義 **流覽查詢**。</span><span class="sxs-lookup"><span data-stu-id="27f40-400">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="27f40-401">選取 **Apply，** 然後 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="27f40-401">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="27f40-402">選取 **儲存** 以儲存儀表板。</span><span class="sxs-lookup"><span data-stu-id="27f40-402">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="27f40-403">現在，您已完成建立您的視圖。</span><span class="sxs-lookup"><span data-stu-id="27f40-403">Now you've completed creating your views.</span></span>

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a><span data-ttu-id="27f40-404">在 中設定通知 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="27f40-404">Configure Alerts in :::no-loc text="Azure Monitor":::</span></span>
<span data-ttu-id="27f40-405"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="27f40-405"><a name="Alerts"> </a></span></span>

<span data-ttu-id="27f40-406">:::no-loc text="Azure Monitor"::: 當主機遇到問題時，可以提醒系統管理員 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="27f40-406">:::no-loc text="Azure Monitor"::: can raise alerts to notify the administrators, when a :::no-loc text="Microsoft Teams Rooms"::: console encounters an issue.</span></span>

<span data-ttu-id="27f40-407">:::no-loc text="Azure Monitor"::: 包含內建的警示機制，會定期執行排程記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="27f40-407">:::no-loc text="Azure Monitor"::: includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="27f40-408">如果記錄搜尋的結果符合特定準則，即會建立通知記錄。</span><span class="sxs-lookup"><span data-stu-id="27f40-408">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="27f40-409">規則接著會自動執行一或多個動作，主動通知您通知或援用另一個程式。</span><span class="sxs-lookup"><span data-stu-id="27f40-409">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="27f40-410">有通知的可能選項有：</span><span class="sxs-lookup"><span data-stu-id="27f40-410">The possible options with alerts are:</span></span>
-   <span data-ttu-id="27f40-411">傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="27f40-411">Sending an email</span></span>
-   <span data-ttu-id="27f40-412">透過 HTTP POST 要求來啟動外部程式</span><span class="sxs-lookup"><span data-stu-id="27f40-412">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="27f40-413">啟動服務中的 :::no-loc text="Azure Automation"::: Runbook</span><span class="sxs-lookup"><span data-stu-id="27f40-413">Starting a runbook in :::no-loc text="Azure Automation"::: service</span></span>

<span data-ttu-id="27f40-414">請參閱[在 中記錄 :::no-loc text="Azure Monitor"::: 通知](/azure/azure-monitor/platform/alerts-unified-log)，以深入瞭解 中的通知 :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="27f40-414">See [Log alerts in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="27f40-415">下列範例在裝置產生硬體或應用程式錯誤時傳送 :::no-loc text="Microsoft Teams Rooms"::: 電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="27f40-415">The following examples send email alerts when a :::no-loc text="Microsoft Teams Rooms"::: device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a><span data-ttu-id="27f40-416">設定硬體問題 :::no-loc text="Microsoft Teams Rooms"::: 的電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="27f40-416">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: hardware issues</span></span>

<span data-ttu-id="27f40-417">設定提醒規則，檢查過去一小時內發生硬體問題的 :::no-loc text="Microsoft Teams Rooms"::: 裝置。</span><span class="sxs-lookup"><span data-stu-id="27f40-417">Configure an alert rule that checks for :::no-loc text="Microsoft Teams Rooms"::: devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="27f40-418">請登錄入口[ :::no-loc text="Microsoft Azure"::: 網站，](https://portal.azure.com)然後 :::no-loc text="Log Analytics"::: 前往並選取您的工作區。</span><span class="sxs-lookup"><span data-stu-id="27f40-418">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="27f40-419">流覽至您的 :::no-loc text="Log Analytics"::: 工作區，然後 **選取通知** ，然後選取 **新增通知規則**</span><span class="sxs-lookup"><span data-stu-id="27f40-419">Navigate to your :::no-loc text="Log Analytics"::: workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="27f40-420">選取 **新增條件** ，然後 **選取自訂記錄搜尋**</span><span class="sxs-lookup"><span data-stu-id="27f40-420">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="27f40-421">在搜尋查詢文字方塊中輸入下列查詢。</span><span class="sxs-lookup"><span data-stu-id="27f40-421">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="27f40-422">設定通知邏輯設定：</span><span class="sxs-lookup"><span data-stu-id="27f40-422">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="27f40-423">**根據：** 結果數目</span><span class="sxs-lookup"><span data-stu-id="27f40-423">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="27f40-424">**條件：** 大於</span><span class="sxs-lookup"><span data-stu-id="27f40-424">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="27f40-425">**閾值：0**</span><span class="sxs-lookup"><span data-stu-id="27f40-425">**Threshold:** 0</span></span><br>

6. <span data-ttu-id="27f40-426">設定評估設定 **，然後選取** 完成 ：</span><span class="sxs-lookup"><span data-stu-id="27f40-426">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="27f40-427">**期間 (分鐘) ：60**</span><span class="sxs-lookup"><span data-stu-id="27f40-427">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="27f40-428">**以 (分鐘) 頻率：60**</span><span class="sxs-lookup"><span data-stu-id="27f40-428">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="27f40-429">設定動作群組：</span><span class="sxs-lookup"><span data-stu-id="27f40-429">Configure action groups:</span></span>
    1.  <span data-ttu-id="27f40-430">選取 **建立新**</span><span class="sxs-lookup"><span data-stu-id="27f40-430">Select **Create New**</span></span>
    2.  <span data-ttu-id="27f40-431">為動作組名和簡短名稱 *欄位\*\*提供適當的* 名稱。</span><span class="sxs-lookup"><span data-stu-id="27f40-431">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="27f40-432">指定唯一 *的動作名稱，* 然後選取 **電子郵件/簡訊/推/語音**，然後選取編輯 **詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="27f40-432">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="27f40-433">選取 **電子郵件** 核取方塊，並提供接收通知之人員或群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="27f40-433">Select the **Email** checkbox and provide the email address of the person or group that will receive the alerts.</span></span>
    5.  <span data-ttu-id="27f40-434">您也可以提供電話號碼，以取得電話、簡訊或兩者的通知。</span><span class="sxs-lookup"><span data-stu-id="27f40-434">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="27f40-435">選取 **確定**。</span><span class="sxs-lookup"><span data-stu-id="27f40-435">Select **OK**.</span></span>

8. <span data-ttu-id="27f40-436">**如果您想要重寫** 通知電子郵件的主題行，請自訂動作。</span><span class="sxs-lookup"><span data-stu-id="27f40-436">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="27f40-437">指定規則名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="27f40-437">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="27f40-438">**規則名稱：** :::no-loc text="Microsoft Teams Rooms"::: 硬體失敗通知</span><span class="sxs-lookup"><span data-stu-id="27f40-438">**Rule Name:** :::no-loc text="Microsoft Teams Rooms"::: Hardware Failure Alert</span></span><br>
    <span data-ttu-id="27f40-439">**描述：** 過去一小時內發生硬體問題的裝置清單</span><span class="sxs-lookup"><span data-stu-id="27f40-439">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="27f40-440">選取預定的嚴重性，然後確認已啟用規則。</span><span class="sxs-lookup"><span data-stu-id="27f40-440">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="27f40-441">選取 **建立警示規則**。</span><span class="sxs-lookup"><span data-stu-id="27f40-441">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a><span data-ttu-id="27f40-442">設定應用程式問題 :::no-loc text="Microsoft Teams Rooms"::: 的電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="27f40-442">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: application issues</span></span>

<span data-ttu-id="27f40-443">重複相同的程式，但使用下列查詢列出過去一小時內遇到應用程式問題的裝置。</span><span class="sxs-lookup"><span data-stu-id="27f40-443">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="27f40-444">現在，您已完成定義通知。</span><span class="sxs-lookup"><span data-stu-id="27f40-444">Now you've completed defining alerts.</span></span> <span data-ttu-id="27f40-445">您可以使用上述範例定義其他警示。</span><span class="sxs-lookup"><span data-stu-id="27f40-445">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="27f40-446">產生通知時，您就會收到一封電子郵件，列出過去一小時內發生問題的裝置。</span><span class="sxs-lookup"><span data-stu-id="27f40-446">When an alert is generated, you'll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="27f40-447">![範例 :::no-loc text="Azure Monitor"::: 通知電子郵件] (。/media/Deploy-Azure-Monitor-6.png「範例 :::no-loc text="Azure Monitor"::: 通知電子郵件」) </span><span class="sxs-lookup"><span data-stu-id="27f40-447">![Sample :::no-loc text="Azure Monitor"::: alert email](../media/Deploy-Azure-Monitor-6.png "Sample :::no-loc text=&quot;Azure Monitor&quot;::: alert email")</span></span>

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a><span data-ttu-id="27f40-448">設定所有裝置 :::no-loc text="Azure Monitoring":::</span><span class="sxs-lookup"><span data-stu-id="27f40-448">Configure all devices for :::no-loc text="Azure Monitoring":::</span></span>
<span data-ttu-id="27f40-449"><a name="configure_all_devices"></a>設定儀表板和通知之後，您可以在所有裝置上設定和設定代理程式， :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 以完成監控部署。</span><span class="sxs-lookup"><span data-stu-id="27f40-449"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure :::no-loc text="Microsoft Monitoring"::: agent on all :::no-loc text="Microsoft Teams Rooms"::: devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="27f40-450">雖然您可以在每個裝置上手動安裝和設定代理程式，但我們強烈建議您 :::no-loc text="Microsoft Monitoring"::: 利用現有的軟體部署工具和方法。</span><span class="sxs-lookup"><span data-stu-id="27f40-450">Although you can install and configure the :::no-loc text="Microsoft Monitoring"::: agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="27f40-451">如果您是第一次建立裝置，您可能會想要將代理程式設定和設定步驟納入您的建立 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: 程式。</span><span class="sxs-lookup"><span data-stu-id="27f40-451">If you're building your :::no-loc text="Microsoft Teams Rooms"::: devices for the first time, you might want to include the :::no-loc text="Microsoft Monitoring"::: agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="27f40-452">詳細資訊，請參閱 [使用命令列安裝代理程式](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="27f40-452">For more information, see [Install the agent using the command line](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="27f40-453">使用 :::no-loc text="Microsoft Monitoring"::: 群組原則物件或 GPO (部署) </span><span class="sxs-lookup"><span data-stu-id="27f40-453">Deploying :::no-loc text="Microsoft Monitoring"::: agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="27f40-454">如果您已經部署您的裝置，然後再進行部署，您可以使用群組原則物件，使用所提供的腳本來設定 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: :::no-loc text="Active Directory"::: 和設定代理程式。</span><span class="sxs-lookup"><span data-stu-id="27f40-454">If you already deployed your :::no-loc text="Microsoft Teams Rooms"::: devices before you implement :::no-loc text="Azure Monitoring":::, you can use the provided script to set up and configure the agents by using :::no-loc text="Active Directory"::: group policy objects.</span></span>

1.  <span data-ttu-id="27f40-455">建立共用網路路徑，並授予網域 **電腦群組的讀取** 存取權。</span><span class="sxs-lookup"><span data-stu-id="27f40-455">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="27f40-456">下載 64 位版本的 :::no-loc text="Microsoft Monitoring"::: Agent，從 :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="27f40-456">Download the 64-bit version of the :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows"::: from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="27f40-457">將設定套件的內容解壓縮到網路共用中。</span><span class="sxs-lookup"><span data-stu-id="27f40-457">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="27f40-458">開啟命令提示視窗，然後執行 **MMASetup-AMD64.exe /c**</span><span class="sxs-lookup"><span data-stu-id="27f40-458">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="27f40-459">指定您剛剛建立共用，然後解壓縮內容。</span><span class="sxs-lookup"><span data-stu-id="27f40-459">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="27f40-460">建立新的群組原則物件，並將其指派給電腦 :::no-loc text="Microsoft Teams Rooms"::: 帳戶所在的組織單位。</span><span class="sxs-lookup"><span data-stu-id="27f40-460">Create a new Group Policy Object and assign it to the organizational unit where :::no-loc text="Microsoft Teams Rooms"::: machine accounts are located.</span></span>

5.  <span data-ttu-id="27f40-461">設定 PowerShell 執行策略：</span><span class="sxs-lookup"><span data-stu-id="27f40-461">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="27f40-462">編輯新建立群組原則物件，並流覽至電腦群組 \\ 策略 \\ 系統管理範本 \\ :::no-loc text="Windows"::: 元件 \\:::no-loc text="Windows PowerShell":::</span><span class="sxs-lookup"><span data-stu-id="27f40-462">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ :::no-loc text="Windows"::: Components \\ :::no-loc text="Windows PowerShell":::</span></span>
    2.  <span data-ttu-id="27f40-463">啟用開啟 **腳本執行，** 並設定 **執行策略** 以 **允許本地腳本**。</span><span class="sxs-lookup"><span data-stu-id="27f40-463">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="27f40-464">設定啟動腳本：</span><span class="sxs-lookup"><span data-stu-id="27f40-464">Configure the startup script:</span></span>
    1.  <span data-ttu-id="27f40-465">複製下列腳本並儲存為Install-MMAgent.ps1。</span><span class="sxs-lookup"><span data-stu-id="27f40-465">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="27f40-466">修改 WorkspaceId、WorkspaceKey 和 SetupPath 參數，以配合您的設定。</span><span class="sxs-lookup"><span data-stu-id="27f40-466">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="27f40-467">編輯相同的群組原則物件，然後流覽至電腦群組 \\ 設定 \\ :::no-loc text="Windows"::: \\ 腳本 (啟動/關機) </span><span class="sxs-lookup"><span data-stu-id="27f40-467">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ :::no-loc text="Windows"::: Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="27f40-468">按兩下以選取 **[啟動**，然後選取 **PowerShell 腳本**。</span><span class="sxs-lookup"><span data-stu-id="27f40-468">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="27f40-469">選取 **顯示檔案**，然後將 **Install-MMAgent.ps1檔案複製到** 該資料夾。</span><span class="sxs-lookup"><span data-stu-id="27f40-469">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="27f40-470">選取 **新增**，然後 **流覽**。</span><span class="sxs-lookup"><span data-stu-id="27f40-470">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="27f40-471">選取您剛才複製的 ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="27f40-471">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="27f40-472">:::no-loc text="Microsoft Teams Rooms"::: 裝置應安裝並設定 :::no-loc text="Microsoft Monitoring"::: 第二次重新開機的代理程式。</span><span class="sxs-lookup"><span data-stu-id="27f40-472">:::no-loc text="Microsoft Teams Rooms"::: devices should install and configure the :::no-loc text="Microsoft Monitoring"::: agent with the second reboot.</span></span>

```PowerShell
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> <span data-ttu-id="27f40-473">當您需要重新設定 [代理程式、 :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/agent-manage) 將其移至不同的工作區，或修改代理設定時，請參閱管理及維護代理一文。</span><span class="sxs-lookup"><span data-stu-id="27f40-473">You can refer to the article [Managing and maintaining the :::no-loc text="Log Analytics"::: agent](/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="27f40-474">其他解決方案</span><span class="sxs-lookup"><span data-stu-id="27f40-474">Additional Solutions</span></span>
<span data-ttu-id="27f40-475"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="27f40-475"><a name="Solutions"> </a></span></span>

<span data-ttu-id="27f40-476">:::no-loc text="Azure Monitor"::: 透過其解決方案庫提供內建的管理解決方案 [，](/azure/azure-monitor/insights/solutions) 進一步説明您監控環境。</span><span class="sxs-lookup"><span data-stu-id="27f40-476">:::no-loc text="Azure Monitor"::: provides built-in management solutions through its [solution gallery](/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="27f40-477">我們強烈建議您新增[通知管理](/azure/azure-monitor/platform/alert-management-solution)與[ :::no-loc text="Azure Log Analytics"::: 代理人員健康](/azure/azure-monitor/insights/solution-agenthealth)狀態解決方案至您的工作區。</span><span class="sxs-lookup"><span data-stu-id="27f40-477">We highly recommend that you add [Alert Management](/azure/azure-monitor/platform/alert-management-solution) and [:::no-loc text="Azure Log Analytics"::: Agent Health](/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="27f40-478">代理程式健康情況解決方案可協助您識別環境中過期或已中斷的代理程式，而警示管理解決方案會提供有關特定期間中已提出之警示 :::no-loc text="Microsoft Monitoring"::: 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="27f40-478">The Agent Health solution can help you identify outdated or broken :::no-loc text="Microsoft Monitoring"::: agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="27f40-479">另請參閱</span><span class="sxs-lookup"><span data-stu-id="27f40-479">See also</span></span>

[<span data-ttu-id="27f40-480">使用 :::no-loc text="Microsoft Teams Rooms"::: 規劃管理 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="27f40-480">Plan :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-plan.md)

[<span data-ttu-id="27f40-481">使用 :::no-loc text="Microsoft Teams Rooms"::: 管理裝置 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="27f40-481">Manage :::no-loc text="Microsoft Teams Rooms"::: devices with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-manage.md)