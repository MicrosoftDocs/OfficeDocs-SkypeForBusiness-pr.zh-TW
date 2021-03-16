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
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams 裝置健康情況監控

Microsoft Teams 系統管理中心的裝置健康情況監控功能讓您主動監控各種 Teams 裝置的健康情況。 監控裝置離線狀態，如果貴組織中受監視的裝置離線，即時接收通知。  

開始之前，您需要在租使用者中建立團隊/頻道的許可權。 [深入瞭解](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)。

## <a name="configure-device-state-rule"></a>設定裝置狀態規則

1. 在 Microsoft Teams 系統管理中心的左側流覽中，選取通知 **&規則**  >  ****。

   ![系統管理中心的規則區段](../media/select-rules.png)

2. 在規則 **頁面中** ，選取 **裝置狀態規則**。

3. 選取裝置以設定啟用通知的狀態規則。

    ![Teams 裝置狀態規則頁面。](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>解譯規則組


|領域 |說明  |
|--------|-------------|
|**規則類型**   |裝置狀態規則可協助您進行有效的管理。 Teams 裝置，並歸類為裝置管理類型。 未來，將會有更多的裝置管理類型規則可供監控其他相關功能 (例如：不健康裝置和裝置登錄狀態) 。|
|**條件**   |您可以監控裝置離線時的健康情況。 [深入瞭解 Teams](https://docs.microsoft.com/microsoftteams/devices/device-management) 系統管理中心中的裝置管理。 |
|**範圍**   |您可以提及規則評估頻率，指定要監視裝置健康情況的頻率。 根據預設，如果團隊裝置離線，將會即時監控裝置。 |
|**裝置使用者**   |您可以根據已登錄的使用者選取裝置，指定哪些裝置需要主動離線監控。 請參閱選取 [裝置以進行配置](#select-devices-for-configuration) ，以進一步瞭解詳細資料。 |
|**動作**  > **頻道通知**   |在動作區段，您可以指定您想要取得通知的團隊頻道。 目前，系統將會建立名為系統管理通知和通知的預設小組，以及名為 **MonitoringAlerts** 的頻道，其中會傳送通知。 <BR/> <BR/> 您的租使用者中的全域系統管理員和 Teams 系統管理員會自動新加入這個預設團隊。|
|**動作**  > **Web上手**   |您也可以使用外部網頁連結或 (功能) 。 指定要送出 JSON 通知負載之網頁搖動區段的外部公用網頁連結 URL。 <BR/> <BR/>  通知有效負載可透過網頁連結，與貴組織的其他系統整合，以建立自訂工作流程。<br/><br/> 

**網頁搖動的 JSON 負載架構：** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **範例 JSON 負載**：<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>選取要配置的裝置

1. 您可以選取已登錄這些裝置的使用者，以選取要監視的 Teams 裝置。 從 **裝置** 使用者區 **段選取** 新增。

2. 選取一或多個您想要監控裝置健康情況狀態的使用者

   ![在裝置健康情況狀態規則中新增使用者。](../media/select-device-users.png )

   選取的使用者清單會顯示在裝置 **使用者區** 段。 您可以新增或移除使用者來修改此清單。

系統將會監控所選使用者清單使用的所有登錄裝置，以檢查離線健康情況狀態。

## <a name="notifications-in-teams-client"></a>Teams 用戶端中的通知

通知會傳送至系統管理通知和通知小組的 **自動建立監控Alerts****頻道。**

裝置離線通知可以包含下列資訊：

- 離線的裝置名稱。
- 離線裝置的使用者。
- 裝置離線的時間。  (目前，時間會以 UTC.) 
- 引發警示的規則類型。
- 為什麼會提出通知。
