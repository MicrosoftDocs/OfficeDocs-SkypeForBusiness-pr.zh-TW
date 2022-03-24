---
title: 會議Teams使用策略式錄製&簡介
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解Teams通話和會議時使用&錄製
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
ms.openlocfilehash: 18e7b02a52a0ddc7c380ed3fb4c5879b45fe18dc
ms.sourcegitcommit: b878c57b8e822913b7aac8c105f476bc4ebfcd7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2022
ms.locfileid: "63761927"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>會議Teams通話以策略為基礎的錄製&簡介

以策略為基礎的錄製可讓採用 Microsoft Teams 進行通話和會議的組織使用系統管理政策，自動錄製和捕獲通話和線上會議，以按照相關公司或法規政策的要求進行後續處理和保留。

Teams功能已增強，可支援整合協力廠商錄製解決方案，包括平臺功能、使用者體驗，以及提供端對端解決方案所需的系統管理介面，以便針對 Teams 通訊進行配置、管理、錄製、儲存及分析。 增強功能包括通訊平臺 API 和錄製事件，提供：

- 跨裝置及所有支援的音訊、視像、螢幕分享和聊天端點，順暢、高品質的媒體捕獲。

- 支援使用者與支援Teams、 (Teams、Teams、PSTN 商務用 Skype通話端點之間的) 

- 合規性錄製的新系統管理政策，包括與現有的Teams系統管理通話和會議工具與政策整合

合規性錄製可在 Microsoft 365 A3/A5/E3/E5/Business 進階版 和 Office 365 A3/A5/E3/E5 使用者上啟用。 

合規性錄製解決方案整合功能也于 Ignite 2019 的合規性錄製與Microsoft Teams[審查](https://myignite.microsoft.com/archives/IG19-VCE40)。

## <a name="teams-interaction-recording-overview"></a>Teams互動錄製概觀

互動錄製使用案例可以有效分成四個主要的錄製功能類別 ：便利性、功能、組織及合法截取，如影像所示：

> [!div class="mx-imgBorder"]
> ![顯示互動錄製內容與原因的螢幕擷取畫面。](media/recording-taxonomy.png "影像顯示錄製類別。")

每個類別對於錄製的啟動方式、錄製內容、錄製位置、收到通知者、誰控制存取權，以及保留的處理方式，都有不同的需求。

| 類型                   | 方便 (一般Teams錄製)  | 組織 - 受規範 (合規性錄製)  |
| ---------------------- | ------------------ | --------------- |
| 引發              | 使用者               | 系統 (系統)   |
| Target (目標)                 | 每通話/會議 | 每一使用者        |
| 儲存體擁有者          | 使用者               | 合規性      |
| 需要通知嗎？ | 是                | 是             |
| Access 擁有者           | 使用者               | 合規性      |
| 保留政策？      | 選用           | 是             |

Teams提供各種功能，方便且實用的錄製會議和[](./cloud-recording.md)即時活動。 組織錄製是指讓採用 Teams 通話和會議的組織，以系統管理政策的方式，自動錄製和捕獲通話和線上會議，以便根據相關公司或法規政策的要求進行後續處理和保留。 根據此政策的使用者會發現，正在錄製與 Teams 的數位互動，但無法停用錄製，且一旦互動完成，將無法存取錄製。 錄製成為適用于 eDiscovery、法律保留及其他公司保留用途之合規性和法務人員所使用之組織檔案的一部分。

## <a name="example-user-needs"></a>範例使用者需求

<table>
<thead>
<tr class="header">
<th>角色</th>
<th>需要</th>
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
<li><p>瞭解為什麼以及如何將錄製原則Teams使用者/端點。</p></li>
<li><p>為組織設定Teams記錄策略。</p></li>
<li><p>監控和疑難排解通話和Teams錄製相關問題。</p></li>
<li><p>使用使用方式、品質和可靠性的營運分析，支援內部合規性人員。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>合規性專員</td>
<td><ul>
<li><p>以Teams地區邊界中符合合規性義務的方式收集所有通訊。</p></li>
<li><p>根據與通訊相關的中繼資料或互動內容搜尋互動。 常見的範例包括：</p>
<ul>
<li><p><strong>元</strong> - 參與者、時間、方向、撥號號碼、起始號碼、自訂商務資料</p></li>
<li><p><strong>內容</strong> – 文字、情緒、語音、相關互動</p></li>
</ul></li>
<li><p>分析收集的通訊並與其互動，包括收集互動時監控互動的能力。</p></li>
<li><p>確保收集通訊的安全性，並防止所有階段遭到竄改。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>解決方案架構概觀

合規性錄製解決方案已與Teams整合，如下圖所示：

> [!div class="mx-imgBorder"]
> ![顯示小組自訂應用程式設定之螢幕擷取畫面。](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "影像顯示當會議或Teams時流程。")

> [!NOTE]
> 此解決方案是專為啟用以策略為基礎的合規性錄製與Teams。 此解決方案的其他用途將不受支援。

## <a name="recorder"></a>答錄機

合規性錄製解決方案的核心元件是錄製器。
錄製器是建立為可縮放的 Azure (bot) 使用[Microsoft](/graph/cloud-communications-concept-overview)通訊平臺，並註冊為 Microsoft Graph。 錄製器提供與通話和Teams通訊平臺[API](/graph/api/resources/communications-api-overview)的直接互動，並提供媒體使用端點。

提供 [範例合規性記錄器應用程式](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) ，顯示如何設定 Bot、建立應用程式實例及指派合規性政策。 範例中也有錄製特定互動的 API 使用方式範例，例如處理來電路由、[](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)變更錄製狀態，[](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)以及移除正在錄製[的使用者](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)。
Graph特定 API 的檔，請參閱此處以更新[RecordingStatus和](/graph/api/call-updaterecordingstatus?tabs=http)[內文集](/graph/api/resources/incomingcontext)。

錄製器服務的確切實現會因合作夥伴而異，但必須設計成支援多個答錄機，才能達到部署高可用性和地理分佈，以降低從 Teams 到錄製器的延遲。 此外，預計錄製器本身在設計時，會考慮復原和重複。

合作夥伴在提交認證解決方案之前，必須先確認 Microsoft Graph 通訊 API 和 SDK 的最低發行版本本，以確保支援合規性錄製整合的所有需求。

合規性錄製案例的兩項基本需求為：

- 錄製器 Bot 必須部署在 Azure 中

- 錄製器 bot 必須在 Azure Windows虛擬機器上執行

Azure 和 Windows VM 需求僅適用于 Teams Bot 元件，這表示合作夥伴可以執行他們選擇的其他平臺，但必須符合合規性錄製的相關績效和功能需求。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>合規性錄製策略指派和置備

IT 系統管理員可以建立和指派合規性錄製政策，決定要錄製哪些使用者，以及每個使用者會使用哪個錄製器。 當通訊互動發生時，系統會自動根據這些策略的組式邀請錄製者參與交談。 合規性錄製原則是使用 [Microsoft PowerShell](./teams-powershell-overview.md) 管理，並可在每個組織的租使用者、每個使用者和安全性群組層級上加以應用。 您可以找到有關 Microsoft Docs 會議 [政策](./meeting-policies-overview.md)、 [通話策略](./teams-calling-policy.md) 和  [群群組原則的資訊](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group)。

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

   請參閱 [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy)。

3. 指派合規性錄製策略給使用者。

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   請參閱 [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy)。

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>使用者體驗

使用用戶端體驗的用戶端Teams啟用通知支援。 體驗可以是視覺或音訊。

**Teams用戶端 - 視覺注意事項**
- 桌面/Web
- 行動 (iOS/Android) 
- Teams手機
- Teams會議室

**其他端點 - 音訊注意事項**
- SIP 電話
- 商務用 Skype
- 音訊會議
- PSTN 來電者

> [!NOTE]
> 會議模式通話佇列不支援合規性錄製。 請使用轉接模式通話佇列。
> 如果使用者遭遇網際網路中斷，且使用 SBA 撥打和接聽 PSTN 通話，合規性錄製將無法進行。

## <a name="compliance-recording-for-teams-certification-programs"></a>認證計畫Teams合規性錄製

除了發佈公開可用的 API，讓合作夥伴能夠開發和整合 CCaaS 解決方案與 Teams 之外，我們還為 Microsoft Teams 認證計畫開發合規性記錄，為客戶提供保證，確保每個參與合作夥伴的解決方案都經過測試與驗證，以提供他們預期從 Microsoft 解決方案獲得的品質、相容性和可靠性。  

下列合作夥伴已認證其適用于Microsoft Teams。<br/><br/>

|夥伴|解決方案網站 |
|:--|:--|
|ASC 技術 |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|配音器 |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|深入技術 |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|好 |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|奧克創新 |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|紅色方塊 |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|奧克創新 |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
下列合作夥伴正在認證其解決方案Microsoft Teams。<br/><br/>

|夥伴|解決方案網站 |
|:--|:--|
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |


隨著更多合作夥伴加入並符合認證準則，這份清單將會更新。

## <a name="next-steps"></a>後續步驟

如果您是想加入認證計畫廠商，請將郵件傳送 [至](mailto:Teamscategorypartner@microsoft.com)Teamscategorypartner@microsoft.com。
