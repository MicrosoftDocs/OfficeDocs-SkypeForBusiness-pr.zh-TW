---
title: 通話&會議的 Teams 原則型錄製簡介
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
description: 瞭解通話&會議的 Teams 原則型錄製
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
- tier3
- purview-compliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088515e6d9d4fe9e6dc893d736f7baac1148c731
ms.sourcegitcommit: 86b9503eb0085e23176cb346767f880ea3a73e77
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2022
ms.locfileid: "68808282"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>通話&會議的 Teams 原則型錄製簡介

原則型錄製可讓採用 Microsoft Teams 進行通話和會議的組織使用系統管理原則，在相關公司或法規原則要求下自動錄製和擷取通話和線上會議以進行後續處理和保留。

Teams 已增強以支援協力廠商錄製解決方案的整合，包括平臺功能、使用者體驗，以及提供端對端解決方案以進行設定、管理、錄製、儲存及分析 Teams 通訊所需的管理介面。 Enhancements include communications platform API and events for recording， which provides：

- 跨裝置以及所有支援的音訊、視訊、螢幕共用和聊天端點，順暢、高品質的媒體擷取。

- 支援 Teams 使用者與 Teams、Teams Mobile、商務用 Skype、PSTN (支援的通話端點之間的互動擷) 取

- 新的合規性記錄系統管理原則，包括與現有的 Teams 系統管理通話和會議工具和原則整合

您可以在 Microsoft 365 A3/A5/E3/E5/Business Premium 和 Office 365 A3/A5/E3/E5 使用者上啟用合規性錄製。 

合規性錄製解決方案整合功能也已在 Ignite 2019 的 [合規性錄製和 Microsoft Teams 會話](https://myignite.microsoft.com/archives/IG19-VCE40)中檢閱。

## <a name="teams-interaction-recording-overview"></a>Teams 互動錄製概觀

互動錄製使用案例可以有效地分成四個主要類別的錄製功能： 便利性、功能性、組織及合法截距，如下圖所示：

> [!div class="mx-imgBorder"]
> ![顯示互動錄製內容和原因的螢幕擷取畫面。](media/recording-taxonomy.png "影像顯示錄製類別。")

每個類別都需要針對錄製的起始方式、錄製內容、儲存錄製的位置、收到通知的人員、控制存取的人員，以及處理保留的方式提出不同的要求。

| 類型                   | 一般 Teams 錄製 (便利性)  | 組織 - 受規範 (合規性記錄)  |
| ---------------------- | ------------------ | --------------- |
| 引發              | 使用者               | 管理員 (系統)   |
| Target (目標)                 | 每次通話 /會議 | 每一使用者        |
| 儲存空間擁有者          | 使用者               | 合規性      |
| 需要通知嗎？ | 是                | 是             |
| 存取擁有者           | 使用者               | 合規性      |
| 保留原則？      | 選用           | 是             |

Teams 提供各種功能，可 [讓您方便](./cloud-recording.md) 且有功能地錄製會議和即時活動。 組織錄製是指讓採用 Teams 進行通話和會議的組織，以系統管理原則的方式，自動記錄和擷取電話和線上會議，以供後續處理和保留，如相關公司或法規原則所要求。 受此原則規範的使用者會發現正在錄製他們與 Teams 的數位互動，但無法停用錄製，而且在互動完成後將無法存取錄製內容。 錄製會成為電子檔探索、法務保留及其他公司保留使用之合規性與法務人員可用之組織封存的一部分。

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
<td>已錄製的使用者</td>
<td><ul>
<li><p>錄製進行中時收到通知。</p></li>
<li><p>當有原則和/或答錄機錯誤導致通話行為變更時，請通知您。</p></li>
</ul></td>
</tr>
<tr class="even">
<td>通訊系統管理員</td>
<td><ul>
<li><p>瞭解為何以及如何將 /強制執行錄製原則套用至 Teams 使用者/端點。</p></li>
<li><p>為組織設定和維護 Teams 錄製原則。</p></li>
<li><p>監控及疑難排解 Teams 通話和會議的錄製相關問題。</p></li>
<li><p>支援內部合規性人員，提供使用方式、品質和可靠性的操作分析。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>法務人員</td>
<td><ul>
<li><p>以符合適當地區邊界之合規性義務所需的方式收集所有 Teams 通訊。</p></li>
<li><p>根據通訊相關中繼資料或互動內容搜尋互動。 常見範例包括：</p>
<ul>
<li><p><strong>元</strong> - 參與者， 時間， 方向， 撥號， 原始號碼， 自訂商務資料</p></li>
<li><p><strong>內容</strong> – 轉譯、情緒、注音、相關互動</p></li>
</ul></li>
<li><p>分析收集的通訊並與之互動，包括在收集互動時監控互動的功能。</p></li>
<li><p>確保收集通訊的安全性，並防止在任何階段發生竄改。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>解決方案架構概觀

合規性錄製解決方案已與 Teams 整合，如下圖所示：

> [!div class="mx-imgBorder"]
> ![顯示小組自訂應用程式設定的螢幕擷取畫面。](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "影像顯示 Teams 會議或電話傳送和接聽時的流程。")

> [!NOTE]
> 此解決方案是專為啟用 Teams 的原則合規性記錄所設計。 將不支援任何其他使用此解決方案的功能。

## <a name="recorder"></a>答錄機

合規性錄製解決方案的核心元件是錄製器。
錄製程式是建置為可縮放的 Azure 服務， (使用 [Microsoft 通訊平臺的](/graph/cloud-communications-concept-overview) Bot) ，並向 Microsoft Graph 註冊為應用程式。 錄製器提供與 Teams 通話和會議 [通訊平臺 API](/graph/api/resources/communications-api-overview) 的直接互動，並提供媒體挪取的端點。

提供 [範例合規性記錄程式應用程式](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) ，示範如何設定 Bot、建立應用程式實例並指派合規性原則。 範例也有 API 使用方式的範例，用於錄製特定互動，例如處理 [來電](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) 路由、 [變更錄製狀態](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)，以及 [移除正在錄製的使用者](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)。
您可以在這裡找到特定 API 的圖形檔，以供 [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) 和 [incomingCoNtext](/graph/api/resources/incomingcontext)使用。

錄製器服務的確切實作會依合作夥伴而有所不同，但必須設計來支援多個記錄器，才能達到高可用性和地理位置分佈的部署，以減少從 Teams 到錄製器的延遲。 此外，預期錄製器本身的設計會考慮到復原和備援。

合作夥伴必須先向 Microsoft 確認 Microsoft Graph 通訊 API 和 SDK 的最低必要發行版本本，才能提交認證解決方案，以確保支援所有合規性錄製整合的需求。

相容性記錄案例的基本需求有兩種：

- 錄製程式機器人必須部署在 Azure 中

- 錄製程式機器人必須在 Azure 的 Windows VM 上執行

Azure 和 Windows VM 需求僅適用于 Teams Bot 元件，這表示只要合作夥伴能夠符合合規性錄製的相關效能和功能需求，合作夥伴就可以實作他們選擇的其餘平臺。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>合規性記錄原則指派和布建

IT 系統管理員可以建立並指派合規性錄製原則，決定要錄製哪些使用者，以及每個使用者將使用哪個錄製器。 當通訊互動進行時，錄製程式會根據這些原則的設定自動受邀參與交談。 合規性記錄原則是使用 [Microsoft PowerShell](./teams-powershell-overview.md) 來管理，而且可以在每個組織的租使用者、每個使用者和安全性群組層級套用。 您可以找到有關 Microsoft Learn for [Meeting 原則](./meeting-policies-overview.md)、 [通話原則](./teams-calling-policy.md) 和  [群組原則的詳細](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group)資訊。

1. 在您的租使用者中建立應用程式實例。

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

2. 建立合規性記錄原則。

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

3. 將合規性錄製原則指派給使用者。

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

系統會使用 Teams 用戶端體驗啟用通知支援。 體驗可以是視覺或音訊。

**Teams 用戶端 - 視覺注意事項**
- 桌面/網頁
- 行動 (iOS/Android) 
- Teams 手機
- Teams 會議室

**其他端點 - 音訊注意事項**
- SIP 手機
- 商務用 Skype
- 音訊會議 (撥入號碼預設或使用者選取語言的音訊通知) 
- PSTN 來電者在 Teams 使用者的預設語言中 (音訊通知) 

> [!NOTE]
> 會議模式通話佇列不支援合規性錄製。 請使用轉接模式通話佇列。
> 如果使用者遇到網際網路中斷，並且使用 SBA 撥打和接聽 PSTN 通話，則合規性錄製將無法運作。

## <a name="compliance-recording-for-teams-certification-programs"></a>Teams 認證程式的合規性記錄

除了發佈可讓合作夥伴開發及整合 CCaaS 解決方案與 Teams 的公開 API 之外，我們還開發了 Microsoft Teams 認證計畫的合規性記錄，讓客戶保證每個合作合作夥伴的解決方案都經過測試和驗證，以提供他們預期從 Microsoft 解決方案獲得的品質、相容性和可靠性。  

下列合作夥伴已認證其 Microsoft Teams 解決方案。<br/><br/>

|夥伴|解決方案網站 |
|:--|:--|
|ASC 技術 |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|深入解析技術 |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|Mida Solutions |[https://www.midasolutions.com/recorder-for-teams/](https://www.midasolutions.com/recorder-for-teams/) |
|NICE Engage |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|NICE NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|樹樹創新 |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|紅色方塊 |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/red-box-partners/microsoft-integration/compliance-recording-for-microsoft-teams)  |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|青色 |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|樹樹創新 |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
下列合作夥伴正在認證其 Microsoft Teams 解決方案。<br/><br/>

|夥伴|解決方案網站 |
|:--|:--|
|GuardRec |[https://www.guardrec.com/en/teams-compliance-recording/](https://www.guardrec.com/en/teams-compliance-recording/) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Redwood Technologies |[https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/](https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/) |


隨著更多合作夥伴加入並符合認證準則，此清單將會更新。


## <a name="next-steps"></a>後續步驟

如果您是尋求加入認證計畫的廠商，請填寫 [此表單](https://aka.ms/CallingPlatformIntake) 做為下一個步驟。 如果您需要提供其他內容和詳細資料，請傳送郵件給 [Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com)。
