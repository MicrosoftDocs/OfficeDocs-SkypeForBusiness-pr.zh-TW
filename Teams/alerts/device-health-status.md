---
title: Microsoft Teams裝置監控和警示
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
description: 瞭解如何使用 Microsoft Teams 系統管理中心的 Teams 監視和警示功能，主動監視 Teams 裝置的健康狀態
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: cca6be8274d26efe661a7a928ebb568aa054cfab2fb62206ee8f3649b37f4ea0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336187"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams 裝置狀況監視

Microsoft Teams 系統管理中心的裝置狀況監視功能可讓您主動監視各種 Teams 裝置的健康情況。 監視裝置的離線狀態，並且在組織中受監視的裝置離線時，即時接收提醒。  

開始之前，您需要在您的租使用者中建立小組/管道建立許可權。 [深入瞭解](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)。

## <a name="configure-device-state-rule"></a>設定裝置狀態規則

1. 在 Microsoft Teams 系統管理中心的左側導覽中，選取 [**通知] & 警示**  >  **規則**。

   ![[規則] 區段中的系統管理中心](../media/select-rules.png)

2. 在 [ **規則** ] 頁面中，選取 [ **裝置狀態規則**]。

3. 選取裝置以設定啟用提醒的狀態規則。

    ![Teams 裝置狀態規則] 頁面。](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>轉譯規則設定


|欄位 |描述  |
|--------|-------------|
|**規則類型**   |裝置狀態規則可協助您有效地進行管理。 Teams 裝置，並歸類為裝置管理類型。 在未來，將會有更多裝置管理類型的規則可供您監視其他相關功能 (範例可能包括：裝置的健康情況，以及裝置) 的登入狀態。|
|**Condition**   |您可以監視裝置的健康情況（如果它們離線）。 [深入瞭解](../devices/device-management.md)Teams 系統管理中心的裝置管理。 |
|**Scope**   |您可以透過提及規則評估頻率，指定要監視裝置健康狀態的頻率。 依預設，小組裝置會在離線時以接近即時監控。 |
|**裝置使用者**   |您可以根據登入的使用者，選取哪些裝置需要主動式 offline statue monitoring。 如需詳細資訊，請參閱 [Select devices for configuration](#select-devices-for-configuration) 。 |
|**動作**  > **通道警示**   |在 [動作] 區段中，您可以指定您想要取得提醒的小組頻道。 目前，將會建立一個名為 **Admin 警示** 的預設小組和一個名為 **MonitoringAlerts** 的頻道，將會在此小組傳送通知。 <BR/> <BR/> 您租使用者中的全域管理員和 Teams 系統管理員會自動新增至此預設團隊。|
|**動作**  > **Webhook**   |您也可以使用外部 webhook (選用) 取得通知。 在 webhook 區段中指定會傳送 JSON 通知負載的外部公用 webhook URL。 <BR/> <BR/>  透過 webhooks 的通知負載可以與組織中的其他系統整合，以建立自訂工作流程。<br/><br/> 

**Webhook 的 JSON 負載架構：** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **範例 JSON 負載**：<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>選取設定的裝置

1. 您可以選取要監視的 Teams 裝置，方法是選取登入這些裝置的使用者。 從 [**裝置使用者**] 區段中，選取 [**新增**]。

2. 選取您要監視裝置健康狀態的一或多個使用者

   ![新增裝置健康狀態規則中的使用者。](../media/select-device-users.png )

   選取的使用者清單會顯示在 [ **裝置使用者** ] 區段中。 您可以新增或移除使用者來修改此清單。

選取的使用者清單所使用的所有登入裝置都會受到離線健康狀態的監視。

## <a name="notifications-in-teams-client"></a>Teams 用戶端中的通知

通知會在系統 **管理員警示和通知** 小組的自動建立 **MonitoringAlerts** 通道中傳遞。

裝置離線通知可包含下列資訊：

- 離線的裝置名稱。
- 離線裝置的使用者。
- 裝置離線的時間。  (目前，時間會以 UTC 顯示。 ) 
- 引發警示的規則類型。
- 為什麼會產生警示。