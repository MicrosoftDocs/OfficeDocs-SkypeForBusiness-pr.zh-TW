---
title: 呼叫 & 會議的小組原則錄製簡介
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: 瞭解團隊原則錄製，以便通話 & 會議
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
ms.openlocfilehash: 00727602aed5eee205a01b01e1ab01218c5b2352
ms.sourcegitcommit: 8acc2ed4cb807f941a6526ec8aad562536f45aa6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44804677"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Callings & 會議的小組原則錄製簡介

原則式錄製：可讓使用管理原則的 Microsoft 團隊運用 Microsoft 團隊進行通話和會議，以便在相關的公司或法規原則所需的後續處理及保留期間自動錄製並捕獲。

團隊已增強，可支援協力廠商錄製解決方案的整合，包括平臺功能、使用者體驗和管理介面，以提供用於設定、管理、錄製、儲存及分析團隊溝通的端對端方案。 這包括通訊平臺 Api 和錄製事件，提供：

- 跨裝置的無縫、高品質媒體捕獲，以及音訊、影片、螢幕共用及聊天的所有支援端點。

- 支援小組使用者與支援的呼叫端點之間的互動捕獲（團隊、團隊行動裝置、商務用 Skype、PSTN）

- 新的合規性記錄管理原則，包括與現有團隊的整合管理通話與會議工具及原則

- 針對有個別授權的小組使用者啟用

相容性錄製解決方案整合功能也會在 Ignite 2019 的[<span class="underline">相容性錄製和 Microsoft 團隊會話</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions)中進行審查。

## <a name="teams-interaction-recording-overview"></a>團隊互動錄製概覽

互動錄製使用案例可以有效地分為四種主要類別的錄製功能-便利性、功能、組織及法律截獲，如影像所示：

![螢幕擷取畫面顯示互動錄製的內容和原因。](media/recording-taxonomy.png "影像會顯示錄製類別。")

每個類別都必須對啟動錄製的方式有不同的需求、錄製的內容、儲存錄製的位置、通知者、控制存取的人員，以及如何處理保留作業。

|                        | 便利性        | 多功能         | 組織-一般      | 組織管制 | 法律截獲   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| 發送              | 使用者               | App/解決方案       | 系統管理員（系統）     | 系統管理員（系統）  | LEA                |
| 目標                 | 每次通話/會議 | 每次通話/會議 | 每次通話/會議 | 每位使用者        | 每個端點/已執行 |
| 儲存擁有者          | 使用者               | 適用                | 管理員              | 從屬      | LEA                |
| 需要通知嗎？ | 是                | 是                | 是                | 是             | 否                 |
| Access 擁有者           | 使用者               | 適用                | 管理員              | 從屬      | LEA                |
| 保留原則？      | 選用           | 是                | 是                | 是             | 是                |

小組提供各種功能，可讓會議與即時事件進行[<span class="underline">便利</span>](https://docs.microsoft.com/microsoftteams/cloud-recording)且正常運作。 組織錄製意味著讓使用團隊進行呼叫與會議 stipulate、使用管理原則進行通話與線上會議時，應依相關的公司或法規原則，自動錄製並捕獲進行後續處理及保留的方式。 此原則下的使用者會發現與小組的數位互動正在錄製，但無法停用錄製，而且在互動完成之後就不能存取錄製。 錄製成為組織封存的一部分，可供電子檔探索、法律封存及其他公司留存用途使用。

## <a name="example-user-needs"></a>使用者需求範例

<table>
<thead>
<tr class="header">
<th><strong>個人</strong></th>
<th><strong>滿足</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>錄製的使用者</td>
<td><ul>
<li><p>在進行錄製時收到通知。</p></li>
<li><p>在原則與/或記錄器錯誤導致通話行為變更時收到通知。</p></li>
</ul></td>
</tr>
<tr class="even">
<td>通訊系統管理員</td>
<td><ul>
<li><p>瞭解為何以及如何將錄製原則套用/強制執行至團隊使用者/端點。</p></li>
<li><p>設定及維護組織的小組記錄原則。</p></li>
<li><p>監視及疑難排解與團隊通話與會議有關的錄製相關問題。</p></li>
<li><p>針對使用方式、品質和可靠性，支援內部合規性監察官與操作分析。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>合規性監察官</td>
<td><ul>
<li><p>收集所有團隊通訊的方式，以符合適當地區界限中的合規性義務所需的方式。</p></li>
<li><p>根據與通訊相關的中繼資料或互動內容來搜尋互動。 常見的範例包括：</p>
<ul>
<li><p><strong>中繼資料</strong> -參與者、時間、方向、撥電話號碼、來源編號、自訂商務資料</p></li>
<li><p><strong>內容</strong>–操作、觀點、拼音、相關互動</p></li>
</ul></li>
<li><p>分析收集的通訊並與之互動，包括在收集時監視互動的能力。</p></li>
<li><p>確保收集的通訊安全，並防止所有階段遭到篡改。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>方案架構概述

合規性錄製解決方案已與團隊整合，如下列圖表所示：

![顯示小組自訂應用程式設定的螢幕擷取畫面](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "影像會顯示當您傳送和接收小組會議或通話時的流程。")

## <a name="recorder"></a>燒錄

[規範錄製] 解決方案的核心元件是錄影機。
錄影機是以可伸縮的 Azure 服務（bot）建立的，可[<span class="underline">利用 microsoft 的通訊平臺</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview)，並使用 microsoft Graph 將其註冊為應用程式。 記錄器提供與團隊通話與會議[<span class="underline">通訊平臺 api</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)的直接互動，並提供媒體攝取的端點。

[<span class="underline">提供範例規範記錄器應用程式</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot)，說明如何設定 bot、建立 app 實例並指派合規性原則。 此範例也會提供用於錄製特定互動（例如處理[<span class="underline">撥入電話</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   路由、[<span class="underline">變更錄製狀態</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)，以及[<span class="underline">移除錄製的使用者</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)）的 API 用法範例。
您可以在這裡找到適用于[<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http)和[<span class="underline">IncomingCoNtext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)的特定 api 的圖形檔。

記錄器服務的確切實現會因合作夥伴而異，但必須設計為支援多個燒錄機，才能實現高可用性和地理位置分佈，以減少團隊的延遲時間。 此外，預期記錄器本身在設計時應考慮復原能力和冗余性。

在提交其認證方案前，合作夥伴必須先確認 Microsoft Graph 通訊 Api 與 Sdk 的最低發行版本本，然後才能提交其認證方案，以確保所有合規性錄製整合需求都受到支援。

針對合規性錄製案例的基本需求，有兩個特殊需求：

- 錄影機 bot 必須部署在 Azure 中

- 錄影機 bot 必須在 Azure 中的 Windows VM 上執行

Azure 和 Windows VM 的需求只適用于 [團隊 Bot] 元件，這表示合作夥伴可能會執行其選擇的其他平臺，前提是他們可以滿足相容性錄製的相關效能與功能需求。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>合規性錄製原則指派與置備

IT 管理員可以透過建立並指派合規性錄製原則，來判斷要錄製哪些使用者，以及每個使用者要使用哪一種記錄器。 當通訊互動發生時，會根據這些原則的設定，自動邀請錄影機參與交談。 合規性錄製原則是使用[<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)來管理，而且可以套用於每個組織的租使用者、每使用者和安全群組層級。 您可以在 Microsoft 檔中找到更多關於[<span class="underline">會議原則</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)、[<span class="underline">通話原則</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy)和[<span class="underline">群組原則</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)的資訊。

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

2. 建立合規性錄製原則。

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

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. 將合規性錄製原則指派給使用者。

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">授與 CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>使用者體驗

已使用團隊用戶端體驗來啟用通知支援。 體驗可以是 [視覺] 或 [音訊]。

**團隊用戶端-視覺通知**
- 桌面/網頁
- 行動裝置（iOS/Android）
- 團隊手機
- 團隊聊天室

**其他端點-音訊通知**
- SIP 電話
- 商務用 Skype
- 音訊會議
- PSTN 呼叫者

## <a name="compliance-recording-for-teams-certification-programs"></a>小組認證程式的合規性錄製

除了發佈公開提供的 Api，讓合作夥伴能夠開發並整合 CCaaS 方案與團隊合作，我們已開發出 Microsoft 團隊認證計畫的規範錄製，為客戶提供每個參與合作夥伴的解決方案都經過測試和驗證，以提供他們預期的品質、相容性及可靠性。  

下列合作夥伴正在為 Microsoft 團隊驗證其解決方案的程式。  

|Partner|解決方案網站 |
|:--|:--|
|ASC 技術 |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|！ |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|紅色方塊 |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

此清單會隨著更多合作夥伴加入並符合認證準則而更新。

## <a name="next-steps"></a>後續步驟

如果您是尋求加入認證計畫的供應商，請<a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>[郵件]。
