---
title: Microsoft Teams 裝置監控與警示
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 瞭解如何在 Microsoft Teams 系統管理中心使用 Teams 監控和警示功能，主動監控 Teams 裝置的健康情況
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 03a57da7af783fa95e0bccbcb6a96f183b2fbb90
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819438"
---
# <a name="microsoft-teams-device-health-monitoring"></a><span data-ttu-id="86e14-103">Microsoft Teams 裝置健康情況監控</span><span class="sxs-lookup"><span data-stu-id="86e14-103">Microsoft Teams device health monitoring</span></span>

<span data-ttu-id="86e14-104">Microsoft Teams 系統管理中心的裝置健康情況監控功能讓您主動監控各種 Teams 裝置的健康情況。</span><span class="sxs-lookup"><span data-stu-id="86e14-104">Device health monitoring in the Microsoft Teams admin center gives you an ability to proactively monitor the health of various Teams devices.</span></span> <span data-ttu-id="86e14-105">監控裝置離線狀態，如果貴組織中受監視的裝置離線，即時接收通知。</span><span class="sxs-lookup"><span data-stu-id="86e14-105">Monitor the offline state of a device and receive alerts in real time if the monitored device in your organization goes offline.</span></span>  

<span data-ttu-id="86e14-106">開始之前，您需要在租使用者中建立團隊/頻道的許可權。</span><span class="sxs-lookup"><span data-stu-id="86e14-106">Before you start, you'll need the teams/channel creation permissions in your tenant.</span></span> <span data-ttu-id="86e14-107">[深入瞭解](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="86e14-107">[Learn More](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).</span></span>

## <a name="configure-device-state-rule"></a><span data-ttu-id="86e14-108">設定裝置狀態規則</span><span class="sxs-lookup"><span data-stu-id="86e14-108">Configure device state rule</span></span>

1. <span data-ttu-id="86e14-109">在 Microsoft Teams 系統管理中心的左側流覽中，選取通知 **&規則**  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="86e14-109">In the left navigation of the Microsoft Teams admin center, select **Notifications & alerts** > **Rules**.</span></span>

   ![系統管理中心的規則區段](../media/select-rules.png)

2. <span data-ttu-id="86e14-111">在規則 **頁面中** ，選取 **裝置狀態規則**。</span><span class="sxs-lookup"><span data-stu-id="86e14-111">In the **Rules** Page, select **Device state rule**.</span></span>

3. <span data-ttu-id="86e14-112">選取裝置以設定啟用通知的狀態規則。</span><span class="sxs-lookup"><span data-stu-id="86e14-112">Select the device to configure the state rule for enabling alerts.</span></span>

    ![Teams 裝置狀態規則頁面。](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a><span data-ttu-id="86e14-114">解譯規則組</span><span class="sxs-lookup"><span data-stu-id="86e14-114">Interpret the rule configuration</span></span>


|<span data-ttu-id="86e14-115">領域</span><span class="sxs-lookup"><span data-stu-id="86e14-115">Field</span></span> |<span data-ttu-id="86e14-116">說明</span><span class="sxs-lookup"><span data-stu-id="86e14-116">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="86e14-117">**規則類型**</span><span class="sxs-lookup"><span data-stu-id="86e14-117">**Rule type**</span></span>   |<span data-ttu-id="86e14-118">裝置狀態規則可協助您進行有效的管理。</span><span class="sxs-lookup"><span data-stu-id="86e14-118">The device state rule helps you effectively manage.</span></span> <span data-ttu-id="86e14-119">Teams 裝置，並歸類為裝置管理類型。</span><span class="sxs-lookup"><span data-stu-id="86e14-119">Teams devices and is classified as a device management type.</span></span> <span data-ttu-id="86e14-120">未來，將會有更多的裝置管理類型規則可供監控其他相關功能 (例如：不健康裝置和裝置登錄狀態) 。</span><span class="sxs-lookup"><span data-stu-id="86e14-120">In the future, more rules of device management type will be available to monitor other related capabilities (examples may include: unhealthy device and the sign-in status of device).</span></span>|
|<span data-ttu-id="86e14-121">**條件**</span><span class="sxs-lookup"><span data-stu-id="86e14-121">**Condition**</span></span>   |<span data-ttu-id="86e14-122">您可以監控裝置離線時的健康情況。</span><span class="sxs-lookup"><span data-stu-id="86e14-122">You can monitor the health of devices if they go offline.</span></span> <span data-ttu-id="86e14-123">[深入瞭解 Teams](https://docs.microsoft.com/microsoftteams/devices/device-management) 系統管理中心中的裝置管理。</span><span class="sxs-lookup"><span data-stu-id="86e14-123">[Learn more](https://docs.microsoft.com/microsoftteams/devices/device-management) about device management in Teams admin center.</span></span> |
|<span data-ttu-id="86e14-124">**範圍**</span><span class="sxs-lookup"><span data-stu-id="86e14-124">**Scope**</span></span>   |<span data-ttu-id="86e14-125">您可以提及規則評估頻率，指定要監視裝置健康情況的頻率。</span><span class="sxs-lookup"><span data-stu-id="86e14-125">You can specify how frequently you want to monitor device health status by mentioning the rule evaluation frequency.</span></span> <span data-ttu-id="86e14-126">根據預設，如果團隊裝置離線，將會即時監控裝置。</span><span class="sxs-lookup"><span data-stu-id="86e14-126">By default teams devices will be monitored in near real time if they go offline.</span></span> |
|<span data-ttu-id="86e14-127">**裝置使用者**</span><span class="sxs-lookup"><span data-stu-id="86e14-127">**Device users**</span></span>   |<span data-ttu-id="86e14-128">您可以根據已登錄的使用者選取裝置，指定哪些裝置需要主動離線監控。</span><span class="sxs-lookup"><span data-stu-id="86e14-128">You can specify which devices need proactive offline statue monitoring by selecting them based on signed-in users.</span></span> <span data-ttu-id="86e14-129">請參閱選取 [裝置以進行配置](#select-devices-for-configuration) ，以進一步瞭解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="86e14-129">Refer to [Select devices for configuration](#select-devices-for-configuration) for more details.</span></span> |
|<span data-ttu-id="86e14-130">**動作**  > **頻道通知**</span><span class="sxs-lookup"><span data-stu-id="86e14-130">**Actions** > **Channel alert**</span></span>   |<span data-ttu-id="86e14-131">在動作區段，您可以指定您想要取得通知的團隊頻道。</span><span class="sxs-lookup"><span data-stu-id="86e14-131">In the Actions section, you can specify teams channels you want to get alerts for.</span></span> <span data-ttu-id="86e14-132">目前，系統將會建立名為系統管理通知和通知的預設小組，以及名為 **MonitoringAlerts** 的頻道，其中會傳送通知。</span><span class="sxs-lookup"><span data-stu-id="86e14-132">Currently, a default team named **Admin Alerts and Notifications** and channel named **MonitoringAlerts** will be created where notifications will be delivered to.</span></span> <BR/> <BR/> <span data-ttu-id="86e14-133">您的租使用者中的全域系統管理員和 Teams 系統管理員會自動新加入這個預設團隊。</span><span class="sxs-lookup"><span data-stu-id="86e14-133">Global administrators and Teams administrators in your tenant will be automatically added to this default team.</span></span>|
|<span data-ttu-id="86e14-134">**動作**  > **Web上手**</span><span class="sxs-lookup"><span data-stu-id="86e14-134">**Actions** > **Webhook**</span></span>   |<span data-ttu-id="86e14-135">您也可以使用外部網頁連結或 (功能) 。</span><span class="sxs-lookup"><span data-stu-id="86e14-135">You can also get notifications with an external webhook (optional).</span></span> <span data-ttu-id="86e14-136">指定要送出 JSON 通知負載之網頁搖動區段的外部公用網頁連結 URL。</span><span class="sxs-lookup"><span data-stu-id="86e14-136">Specify an external public webhook URL in the webhook section where a JSON notification payload will be sent.</span></span> <BR/> <BR/>  <span data-ttu-id="86e14-137">通知有效負載可透過網頁連結，與貴組織的其他系統整合，以建立自訂工作流程。</span><span class="sxs-lookup"><span data-stu-id="86e14-137">The notification payload, via webhooks, can be integrated with other systems in your organization to create custom workflows.</span></span><br/><br/> 

<span data-ttu-id="86e14-138">**網頁搖動的 JSON 負載架構：**</span><span class="sxs-lookup"><span data-stu-id="86e14-138">**JSON payload schema for webhook:**</span></span> <BR/><BR/>
<span data-ttu-id="86e14-139"><pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/></span><span class="sxs-lookup"><span data-stu-id="86e14-139"><pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/></span></span> 

  <span data-ttu-id="86e14-140">**範例 JSON 負載**：</span><span class="sxs-lookup"><span data-stu-id="86e14-140">**Sample JSON payload**:</span></span><br/> <br/> <pre lang="JSON">    { <br/>      <span data-ttu-id="86e14-141">"AlertTitle":"*sample_device_name* of *User_Name* has become offline",</span><span class="sxs-lookup"><span data-stu-id="86e14-141">"AlertTitle":"*sample_device_name* of *User_Name* has become offline",</span></span><br/>      <span data-ttu-id="86e14-142">"DeviceLoggedInUserId": *User_GUID* ,</span><span class="sxs-lookup"><span data-stu-id="86e14-142">"DeviceLoggedInUserId": *User_GUID* ,</span></span><br/>      <span data-ttu-id="86e14-143">"DeviceId": *Device_GUID* , </span><span class="sxs-lookup"><span data-stu-id="86e14-143">"DeviceId": *Device_GUID* , </span></span><br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       <span data-ttu-id="86e14-144">"TenantId": *Tenant_GUID* , </span><span class="sxs-lookup"><span data-stu-id="86e14-144">"TenantId": *Tenant_GUID* , </span></span><br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a><span data-ttu-id="86e14-145">選取要配置的裝置</span><span class="sxs-lookup"><span data-stu-id="86e14-145">Select devices for configuration</span></span>

1. <span data-ttu-id="86e14-146">您可以選取已登錄這些裝置的使用者，以選取要監視的 Teams 裝置。</span><span class="sxs-lookup"><span data-stu-id="86e14-146">You can select Teams devices you want to monitor by selecting users signed in to those devices.</span></span> <span data-ttu-id="86e14-147">從 **裝置** 使用者區 **段選取** 新增。</span><span class="sxs-lookup"><span data-stu-id="86e14-147">Select **Add** from the **Device users** section.</span></span>

2. <span data-ttu-id="86e14-148">選取一或多個您想要監控裝置健康情況狀態的使用者</span><span class="sxs-lookup"><span data-stu-id="86e14-148">Select one or more users for which you want to monitor device health state</span></span>

   ![在裝置健康情況狀態規則中新增使用者。](../media/select-device-users.png )

   <span data-ttu-id="86e14-150">選取的使用者清單會顯示在裝置 **使用者區** 段。</span><span class="sxs-lookup"><span data-stu-id="86e14-150">The selected list of users shows in **Device users** section.</span></span> <span data-ttu-id="86e14-151">您可以新增或移除使用者來修改此清單。</span><span class="sxs-lookup"><span data-stu-id="86e14-151">You can modify this list by adding or removing users.</span></span>

<span data-ttu-id="86e14-152">系統將會監控所選使用者清單使用的所有登錄裝置，以檢查離線健康情況狀態。</span><span class="sxs-lookup"><span data-stu-id="86e14-152">All the sign-in devices used by the selected list of users will be monitored for the offline health state.</span></span>

## <a name="notifications-in-teams-client"></a><span data-ttu-id="86e14-153">Teams 用戶端中的通知</span><span class="sxs-lookup"><span data-stu-id="86e14-153">Notifications in Teams client</span></span>

<span data-ttu-id="86e14-154">通知會傳送至系統管理通知和通知小組的 **自動建立監控Alerts\*\*\*\*頻道。**</span><span class="sxs-lookup"><span data-stu-id="86e14-154">The notifications are delivered in the auto-created **MonitoringAlerts** channel of the **Admin Alerts and Notifications** Team.</span></span>

<span data-ttu-id="86e14-155">裝置離線通知可以包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="86e14-155">A device offline notification can include the following information:</span></span>

- <span data-ttu-id="86e14-156">離線的裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="86e14-156">The device name that's offline.</span></span>
- <span data-ttu-id="86e14-157">離線裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="86e14-157">The user of the offline device.</span></span>
- <span data-ttu-id="86e14-158">裝置離線的時間。</span><span class="sxs-lookup"><span data-stu-id="86e14-158">What time the device went offline.</span></span> <span data-ttu-id="86e14-159"> (目前，時間會以 UTC.) </span><span class="sxs-lookup"><span data-stu-id="86e14-159">(Currently, the time is presented in UTC.)</span></span>
- <span data-ttu-id="86e14-160">引發警示的規則類型。</span><span class="sxs-lookup"><span data-stu-id="86e14-160">The type of rule that raised the alert.</span></span>
- <span data-ttu-id="86e14-161">為什麼會提出通知。</span><span class="sxs-lookup"><span data-stu-id="86e14-161">Why an alert is raised.</span></span>
