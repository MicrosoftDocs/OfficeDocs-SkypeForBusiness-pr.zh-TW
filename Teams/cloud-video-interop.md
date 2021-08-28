---
title: Microsoft Teams 雲端視訊 Interop。
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: 使用雲端視像交互操作做為中間解決方案，讓協力廠商會議室裝置加入Microsoft Teams會議。
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39452a659f1a95d66aeac4a18a4d7801764437ae
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618639"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams 雲端視訊 Interop。

雲端視 (CVI) 是 Microsoft 合格協力廠商解決方案，可讓協力廠商會議室 (網真) 和個人視像裝置 (RVC) 加入 Microsoft Teams 會議。
 
有了Microsoft Teams，您可以在會議取得豐富的線上內容共同功能，包括音訊、視像和內容共用。 您可以透過桌面和 Web 用戶端，以及透過許多原生與網路整合的合作夥伴裝置Microsoft Teams。 不過，許多客戶已經投資在視距電話會議和個人視像通訊裝置上，升級可能會非常貴。 雲端視像交互操作提供簡單的解決方案，讓您持續使用現有的解決方案，直到您準備好升級。

使用雲端視Microsoft Teams，所有參與者都享有原生會議體驗 ，包括會議室或用戶端Teams體驗。

### <a name="is-cloud-video-interop-for-me"></a>我是否適合使用雲端視像交互操作？

雲端視像交互操作提供一個中間服務，同時您Microsoft Teams完整原生解決方案，Teams端點。 提供的服務應該是移移路徑的一部分。

雲端視訊交互操作適用于符合下列準則的客戶：

- 有大型會議室裝置和個人視 (部署) 超過 50 個Microsoft Teams
- 我們的其中一個雲端視像交互操作合作夥伴支援
- 在移向原生會議室解決方案期間，想要保留目前會議室裝置和個人視Microsoft Teams投資價值

雖然雲端視像交互操作提供很好的中間解決方案，但我們鼓勵客戶長期研究原生 Teams 會議解決方案，例如 Teams 會議室系統。 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365美國政府和協力廠商服務

Office 365提供將協力廠商應用程式整合至 SharePoint Online 網站、商務用 Skype、Teams、Office Microsoft 365 Apps 企業版 (應用程式的能力，例如 Word、Excel、PowerPoint 和 Outlook) 和 Outlook Web App。 此外，Office 365支援協力廠商服務提供者的整合。 這些協力廠商應用程式和服務可能涉及在 Office 365 基礎結構外的協力廠商系統上儲存、傳送及處理貴組織的客戶資料，因此未涵蓋 Office 365 合規性和資料保護承諾。 **建議您在評估貴組織適當使用這些服務時，審查協力廠商所提供的隱私權和合規性聲明。**



### <a name="partners-certified-for-microsoft-teams"></a>合作夥伴已Microsoft Teams

下列合作夥伴提供適用于 Microsoft Teams 的視Microsoft Teams。 您的公司可能會選擇在企業內與這些合作夥伴的任何組合合作。 

|夥伴|合作夥伴解決方案|
|----|---|
|![代表 Poly RealConnect 的標誌](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a> |
|![代表 Pexip 無限的標誌](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip 無限Microsoft Teams</a> | 
|![代表 BlueJeans 閘道的標誌](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans 閘道Microsoft Teams</a> |
|![代表 Cisco CVI 的標誌](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex 影片整合Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>雲端視像交互操作概觀

Cloud Video Interop 是我們的合作夥伴提供的協力廠商服務，提供現有視訊會議與內部部署個人視Microsoft Teams。

我們的合作夥伴提供的解決方案包含可部署完全雲端或部分/完全內部部署的元件。 
     
下圖顯示合作夥伴解決方案的高層級架構。

![說明雲端視Teams交互操作合作夥伴解決方案的圖表](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>部署雲端視像交互操作

部署雲端視像交互操作解決方案時，您必須瞭解您部署的合作夥伴解決方案。 以下圖表列出部署雲端視像交互操作時應該採取一般步驟。

![描述在貴組織中部署 CVI 的圖表](media/deploying-cvi.png)

### <a name="plan"></a>規劃

在計畫階段期間，您應該找出不會以原生 Teams 取代的裝置，並尋找可支援這些裝置的雲端視像交互操作合作夥伴。  

另外，您必須瞭解，每位將排程會議的使用者都需要授權，才能讓啟用雲端視像交互操作功能的裝置加入會議。 請注意，確切的授權需求可以從雲端視像交互操作合作夥伴取得。 在您開始部署之前，請確保清除這一點。

### <a name="configure"></a>配置

您為 CVI 部署選擇的合作夥伴會提供完整的部署檔，該檔包含在貴組織中成功部署所需的所有步驟。 這包括防火牆埠和 IP 範圍、裝置設定變更，以及其他需要變更的設定。

### <a name="provision"></a>提供  

在部署階段期間，您將根據合作夥伴組組指南指派授權給適當的使用者。 您也需要執行 Azure 同意程式，才能讓合作夥伴存取您的Teams環境。 有關[Azure 同意程式Microsoft 身分識別平臺，](/azure/active-directory/develop/v2-permissions-and-consent)請參閱在 Microsoft 身分識別平臺 端點中的許可權與同意。

### <a name="schedule"></a>附表

在使用者啟用雲端視像交互操作之後，任何使用 Outlook 或 Teams 用戶端的 Teams 會議附加元件排定的會議，都會在 Teams 會議中自動新增適當的額外資訊，以便雲端視像交互操作相容裝置可以加入這些會議。

### <a name="join"></a>加入

視合作夥伴解決方案的不同，有多種方式可以加入啟用雲端視像交互操作的會議。 您的雲端視像交互操作合作夥伴會提供確切的會議加入案例。 我們在下面列出一些範例：

- IVR (互動式語音回應)  
  - 您可以使用電話號碼撥入合作夥伴的 IVR tenantkey@domain。
  - 當您在合作夥伴 IVR 中時，系統會提示您輸入 VTC meetingId，然後將您Teams會議。
- 直撥 
  - 您可以使用直接撥號功能，Teams租使用者金鑰的完整字串，直接撥入會議，而不與合作夥伴的 IVR 互動。VTC ConferenceId@domain。
- 單鍵撥號 
  - 如果您有整合式Teams，您可以使用合作夥伴提供的單鍵撥號功能 (不需要輸入任何撥號字串) 。

## <a name="manage-cloud-video-interop"></a>管理雲端視像交互操作

部署雲端視像交互操作之後，您可以使用合作夥伴提供的解決方案來管理裝置。 每個合作夥伴都會提供一個包含授權和裝置管理的管理介面。 

報告也可以直接從合作夥伴系統管理介面使用。 如需報告功能詳細資訊，請聯絡您所選擇的合作夥伴。 

### <a name="troubleshooting-cloud-video-interop"></a>雲端視像交互操作疑難排解

雲端視像交互操作是合作夥伴提供的服務。 如果您遇到問題，第一個步驟是連接已安裝 Teams 用戶端的裝置，並連接到與造成問題的雲端視音訊交互操作裝置相同的區段。 

如果Teams功能正確，而且您也遵循合作夥伴提供的所有網路和組組指導方針，您必須與合作夥伴聯繫以進行進一步的疑難排解。 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell for Cloud Video Interop

下列 PowerShell Cmdlet 可供您部分 (，) 雲端視像交互操作部署。

- **Get-CsTeamsVideoInteropServicepolicy：Microsoft** 會針對每個支援的合作夥伴提供預先建構的策略，讓您指定要用於雲端視訊交互 () 的合作夥伴。<br>此 Cmdlet 可讓您識別可在貴組織中使用的預先建構策略。 您可以使用 Cmdlet，將這個Grant-CsTeamsVideoInteropServicePolicy指派給一或多個使用者。
- **Grant-CsTeamsVideoInteropServicePolicy：** 此 Cmdlet 可讓您指派預先建構的策略，供貴組織使用，或將策略指派給特定使用者。
- **New-CsVideoInteropServiceProvider：** 使用此 Cmdlet 來指定貴組織想使用之支援的 CVI 合作夥伴相關資訊。
- **Set-CsVideoInteropServiceProvider：** 使用此 Cmdlet 更新貴組織使用之支援 CVI 合作夥伴的資訊。
- **Get-CsVideoInteropServiceProvider：** 使用此 Cmdlet 取得組織中所有已配置的提供者。
- **Remove-CsVideoInteropServiceProvider：** 使用此 Cmdlet 移除貴組織不再使用之提供者的所有提供者資訊。