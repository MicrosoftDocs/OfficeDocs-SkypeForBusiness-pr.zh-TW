---
title: 會議通話的 Teams 策略型錄製簡介&簡介
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: 瞭解會議通話的 Teams &錄製
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7972febeab134f0ec075418e351c35ef7e273fcf
ms.sourcegitcommit: f22e050213798a8ff69c6d502a2fc142104ab213
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51439668"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>會議通話的 Teams &簡介

以策略為基礎的錄製可讓採用 Microsoft Teams 進行通話和會議的組織，使用系統管理政策，自動錄製和捕獲通話和線上會議，以按照相關公司或法規政策的要求進行後續處理和保留。

Teams 已經過增強，可支援整合協力廠商錄製解決方案，包括平臺功能、使用者體驗，以及提供端對端解決方案所需的系統管理介面，以用於配置、管理、錄製、儲存及分析 Teams 通訊。 增強功能包括通訊平臺 API 和錄製事件，提供：

- 跨裝置及所有支援的音訊、視像、螢幕分享和聊天端點，順暢、高品質的媒體捕獲。

- 支援 Teams 使用者與支援的通話端點之間的互動 (Teams、Teams Mobile、商務用 Skype、PSTN) 

- 合規性錄製的新系統管理政策，包括與現有的 Teams 系統管理通話和會議工具與政策整合

Microsoft 365 A3/A5/E3/E5/Business Premium 和 Office 365 A3/A5/E3/E5 使用者可以啟用合規性錄製功能。 

合規性錄製解決方案整合功能也于 Ignite 2019 的合規性錄製和 Microsoft Teams 會話中 [<span class="underline">受到審查</span>](https://myignite.microsoft.com/archives/IG19-VCE40)。

## <a name="teams-interaction-recording-overview"></a>Teams 互動錄製概觀

互動錄製使用案例可以有效分成四個主要的錄製功能類別 ：便利性、功能、組織及合法截取，如影像所示：

![顯示互動錄製內容與原因的螢幕擷取畫面。](media/recording-taxonomy.png "影像顯示錄製類別。")

每個類別對於錄製的啟動方式、錄製內容、錄製位置、收到通知者、誰控制存取權，以及保留的處理方式，都有不同的需求。

| 類型                   | 方便 (一般 Teams 錄製)  | 組織 - 受規範 (合規性錄製)  |
| ---------------------- | ------------------ | --------------- |
| 引發              | 使用者               | 系統 (系統)   |
| 目標                 | 每通話/會議 | 每個使用者        |
| 儲存空間擁有者          | 使用者               | 合規性      |
| 需要通知嗎？ | 是                | 是             |
| Access 擁有者           | 使用者               | 合規性      |
| 保留政策？      | 選用           | 是             |

Teams 提供各種功能，方便 [<span class="underline">且</span>](./cloud-recording.md) 實用的會議與即時活動錄製。 組織錄製是指讓採用 Teams 通話和會議的組織，以系統管理政策的方式，自動錄製和捕獲通話和線上會議，以便根據相關公司或法規政策的要求進行後續處理和保留。 根據此政策的使用者會發現，正在錄製與 Teams 的數位互動，但無法停用錄製，且一旦互動完成，將無法存取錄製。 錄製成為適用于 eDiscovery、法律保留及其他公司保留用途之合規性和法務人員使用之組織檔案的一部分。

## <a name="example-user-needs"></a>範例使用者需求

<table>
<thead>
<tr class="header">
<th><strong>角色</strong></th>
<th><strong>需要</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>錄製的使用者</td>
<td><ul>
<li><p>進行錄製時收到通知。</p></li>
<li><p>當策略和/或答錄機錯誤導致通話行為變更時，請通知。</p></li>
</ul></td>
</tr>
<tr class="even">
<td>通訊系統管理員</td>
<td><ul>
<li><p>瞭解為什麼以及如何將錄製原則適用于 Teams 使用者/端點。</p></li>
<li><p>為組織設定及維護 Teams 錄製政策。</p></li>
<li><p>監控和疑難排解 Teams 通話和會議錄製相關問題。</p></li>
<li><p>使用使用方式、品質和可靠性的營運分析，支援內部合規性人員。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>合規性專員</td>
<td><ul>
<li><p>收集所有 Teams 通訊的方式，以在適當的地區邊界符合合規性義務的方式。</p></li>
<li><p>根據與通訊相關的中繼資料或互動內容搜尋互動。 常見的範例包括：</p>
<ul>
<li><p><strong>中繼資料</strong> - 參與者、時間、方向、撥號號碼、起始號碼、自訂商務資料</p></li>
<li><p><strong>內容</strong> – 文字、情緒、語音、相關互動</p></li>
</ul></li>
<li><p>分析收集的通訊並與其互動，包括收集互動時監控互動的能力。</p></li>
<li><p>確保收集通訊的安全性，並防止所有階段遭到竄改。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>解決方案架構概觀

合規性錄製解決方案已與 Teams 整合，如下圖所示：

![顯示小組自訂應用程式設定之螢幕擷取畫面](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "影像顯示 Teams 會議或通話的接收和接收流程。")

## <a name="recorder"></a>答錄機

合規性錄製解決方案的核心元件是答錄機。
錄製器是建立為可縮放的 Azure 服務， (機器人) 利用 [<span class="underline">Microsoft</span>](/graph/cloud-communications-concept-overview) 的通訊平臺，並註冊為 Microsoft Graph 的應用程式。 錄製器提供與 Teams 通話和會議通訊平臺 [<span class="underline">API</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 的直接互動，並提供媒體使用端點。

提供 [<span class="underline">範例合規性記錄器應用程式</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) ，顯示如何設定 Bot、建立應用程式實例及指派合規性政策。 範例中也有用於錄製特定互動的 API 使用方式範例，例如處理[<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)來電路由、變更[<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)錄製狀態，以及移除正在錄製[<span class="underline">的使用者</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)。
您可以在這裡找到特定 API 上的圖形檔，以用於[<span class="underline">updateRecordingStatus 和</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) [<span class="underline">incomingCoNtext。</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0)

錄製器服務的確切實現會因合作夥伴而異，但必須設計成支援多個答錄機，才能達到部署的高可用性和地理分佈，以降低 Teams 到錄製器的延遲。 此外，預計錄製器本身在設計時，會考慮復原和重複。

合作夥伴在提交認證解決方案之前，必須先確認 Microsoft Graph 通訊 API 和 SDK 的最低發行版本本，以確保支援合規性錄製整合的所有需求。

合規性錄製案例的兩項基本需求為：

- 錄製器 Bot 必須部署在 Azure 中

- 錄製器 Bot 必須在 Azure 的 Windows VM 上執行

Azure 和 Windows VM 需求僅適用于 Teams Bot 元件，這表示合作夥伴可以執行他們選擇的其他平臺，但必須符合合規性錄製的相關績效和功能需求。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>合規性錄製策略指派和置備

IT 系統管理員可以建立和指派合規性錄製政策，決定要錄製哪些使用者，以及每個使用者會使用哪個錄製器。 當通訊互動發生時，系統會自動根據這些策略的組式邀請錄製者參與交談。 合規性錄製原則是使用 [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) 管理，並可在每個組織的租使用者、每個使用者和安全性群組層級上加以應用。 您可以找到有關 Microsoft Docs [<span class="underline">會議政策</span>](./meeting-policies-in-teams.md)、通話 [<span class="underline">策略</span>](./teams-calling-policy.md) 和  [<span class="underline">群群組原則的更多資訊</span>](./assign-policies.md#assign-a-policy-to-a-group)。

1. 在租使用者中建立應用程式實例。

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. 建立合規性錄製政策。

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. 指派合規性錄製策略給使用者。

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span>](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>使用者體驗

使用 Teams 用戶端體驗啟用通知支援。 體驗可以是視覺或音訊。

**Teams 用戶端 - 視覺注意事項**
- 桌面/Web
- 行動 (iOS/Android) 
- Teams 電話
- Teams 會議室

**其他端點 - 音訊注意事項**
- SIP 電話
- 商務用 Skype
- 音訊會議
- PSTN 來電者

## <a name="compliance-recording-for-teams-certification-programs"></a>Teams 認證計畫合規性錄製

除了發佈公開可用的 API，讓合作夥伴能夠開發 CCaaS 解決方案並整合 Teams 之外，我們開發 Microsoft Teams 認證計畫的合規性記錄，為客戶提供保證，確保每個參與合作夥伴的解決方案都經過測試與驗證，以提供他們預期從 Microsoft 解決方案獲得的品質、相容性和可靠性。  

下列合作夥伴已認證其 Microsoft Teams 解決方案。

|夥伴|解決方案網站 |
|:--|:--|
|ASC 技術 |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|音訊代碼 |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|配音器 |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|好 |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


下列合作夥伴正在認證其 Microsoft Teams 解決方案。

|夥伴|解決方案網站 |
|:--|:--|
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|奧克創新 |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|紅色方塊 |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |

隨著更多合作夥伴加入並符合認證準則，這份清單將會更新。

## <a name="next-steps"></a>後續步驟

如果您是想加入認證計畫廠商，請寄郵件<a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com。</a>
