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
description: 使用雲端視像交互操作做為中間解決方案，讓協力廠商會議室裝置加入 Microsoft Teams 會議。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a8d657e2cbc12695453e26ef0e4bf9ad55070bf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122357"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams 雲端視訊 Interop。

雲端視 (CVI) 是 Microsoft 合格協力廠商解決方案，可讓協力廠商會議室 (網真) 和個人視像裝置 (RVC) 加入 Microsoft Teams 會議。
 
有了 Microsoft Teams，您可以在會議取得豐富的線上內容共同功能，包括音訊、視像和內容共用。 您可以透過桌面和 Web 用戶端，以及許多原生與 Microsoft Teams 整合的合作夥伴裝置來享受這項功能。 不過，許多客戶已經投資在視距電話會議和個人視像通訊裝置上，升級可能會非常貴。 雲端視像交互操作提供簡單的解決方案，讓您持續使用現有的解決方案，直到您準備好升級。

Microsoft Teams 使用雲端視像交互操作功能，為所有參與者提供原生會議體驗 ，包括會議室或 Teams 用戶端內部。

### <a name="is-cloud-video-interop-for-me"></a>我是否適合使用雲端視像交互操作？

當您使用 Teams 端點轉換至完整原生 Microsoft Teams 解決方案時，雲端視像交互操作會提供一個中間服務。 提供的服務應該是移移路徑的一部分。

雲端視訊交互操作適用于符合下列準則的客戶：

- 在超過 50 個 (裝置上部署會議室裝置和個人視) ，但無法與 Microsoft Teams 直接整合
- 我們的其中一個雲端視像交互操作合作夥伴支援
- 想要在移向原生 Microsoft Teams 解決方案期間，保留目前會議室裝置和個人視像裝置的投資價值

雖然雲端視像交互操作提供很好的中間解決方案，但我們鼓勵客戶長期研究原生的 Teams 會議解決方案 ，例如 Teams 會議室系統。 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 美國政府版和協力廠商服務

Office 365 提供將協力廠商應用程式整合至 SharePoint Online 網站、商務用 Skype、Teams、企業用 Microsoft 365 應用程式中包含的 Office 應用程式 (例如 Word、Excel、PowerPoint 和 Outlook) 和 Outlook Web App 的能力。 此外，Office 365 支援協力廠商服務提供者的整合。 這些協力廠商應用程式和服務可能涉及在 Office 365 基礎結構外的協力廠商系統上儲存、傳送及處理貴組織的客戶資料，因此不在 Office 365 合規性和資料保護承諾的涵蓋範圍。 **建議您在評估貴組織適當使用這些服務時，審查協力廠商所提供的隱私權與合規性聲明。**



### <a name="partners-certified-for-microsoft-teams"></a>Microsoft Teams 合作夥伴認證

下列合作夥伴提供適用于 Microsoft Teams 的影片交互操作解決方案。 您的公司可能會選擇在企業內與這些合作夥伴的任何組合合作。 

|夥伴|合作夥伴解決方案|
|----|---|
|![代表 Poly RealConnect 的標誌](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a> |
|![代表 Pexip 無限的標誌](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft Teams 的 Pexip 無限</a> | 
|![代表 BlueJeans 閘道的標誌](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft Teams 的 BlueJeans 閘道</a> |
|![代表 Cisco CVI 的標誌](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Microsoft Teams 的 Cisco Webex 影片整合</a>|

### <a name="cloud-video-interop-overview"></a>雲端視像交互操作概觀

Cloud Video Interop 是一項協力廠商服務，由我們的合作夥伴提供，提供現有視訊會議與內部部署個人視像裝置解決方案與 Microsoft Teams 之間的互通性。

我們的合作夥伴提供的解決方案包含可部署完全雲端或部分/完全內部部署的元件。 
     
下圖顯示合作夥伴解決方案的高層級架構。

![描述 Teams Cloud Video Interop 合作夥伴解決方案的圖表](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>部署雲端視像交互操作

部署雲端視像交互操作解決方案時，您必須瞭解您部署的合作夥伴解決方案。 以下圖表列出部署雲端視像交互操作時應該採取一般步驟。

![描述在貴組織中部署 CVI 的圖表](media/deploying-cvi.png)

### <a name="plan"></a>規劃

在計畫階段期間，您應該找出不會以原生 Teams 裝置取代的裝置，並尋找可支援這些裝置的雲端視像交互操作合作夥伴。  

另外，您必須瞭解，每位將排程會議的使用者都需要授權，才能讓啟用雲端視像交互操作功能的裝置加入會議。 請注意，確切的授權需求可以從雲端視像交互操作合作夥伴取得。 在您開始部署之前，請確保清除這項功能。

### <a name="configure"></a>配置

您選擇進行 CVI 部署的合作夥伴會提供完整的部署檔，該檔包含在貴組織中成功部署所需的所有步驟。 這包括防火牆埠和 IP 範圍、裝置設定變更，以及其他需要變更的設定。

### <a name="provision"></a>提供  

在部署階段期間，您將根據合作夥伴組組指南指派授權給適當的使用者。 您也需要執行 Azure 同意程式，才能讓合作夥伴存取您的 Teams 環境。 請參閱 [Microsoft 身分識別平臺端點](/azure/active-directory/develop/v2-permissions-and-consent) 的許可權與同意，以取得 Azure 同意程式詳細資訊。

### <a name="schedule"></a>附表

使用者啟用雲端視像交互操作後，任何使用 Teams 會議 Outlook 會議附加元件或 Teams 用戶端排程的會議，都會自動將適當的額外資訊新加入 Teams 會議，讓雲端視像交互操作相容的裝置可以加入這些會議。

### <a name="join"></a>加入

根據合作夥伴解決方案，有幾種方法可以加入啟用雲端視像交互操作的會議。 您的雲端視像交互操作合作夥伴會提供確切的會議加入案例。 我們在下面列出一些範例：

- IVR (互動式語音回應)  
  - 您可以使用電話號碼撥入合作夥伴的 IVR tenantkey@domain。
  - 當您在合作夥伴 IVR 中時，系統會提示您輸入 VTC meetingId，然後將您連接到 Teams 會議。
- 直撥 
  - 您可以使用直接撥號功能，使用完整的租使用者金鑰字串，直接撥入 Teams 會議，而不與合作夥伴的 IVR 互動。VTC ConferenceId@domain。
- 單鍵撥號 
  - 如果您有整合的 Teams 會議室，您可以使用合作夥伴提供的單鍵撥號功能 (不需要輸入任何撥號字串) 。

## <a name="manage-cloud-video-interop"></a>管理雲端視像交交互操作

部署雲端視像交互操作之後，您可以使用合作夥伴提供的解決方案來管理裝置。 每個合作夥伴都會提供一個包含授權和裝置管理的管理介面。 

報告也可以直接從合作夥伴系統管理介面使用。 如需報告功能詳細資訊，請聯絡您所選擇的合作夥伴。 

### <a name="troubleshooting-cloud-video-interop"></a>雲端視像交互操作疑難排解

雲端視像交互操作是合作夥伴提供的服務。 如果您遇到問題，第一個步驟是連接已安裝 Teams 用戶端的裝置，並連接到與造成問題的雲端視像交互操作裝置相同的區段。 

如果 Teams 在此區段中能正確工作，而且您也遵循合作夥伴提供的所有網路和組組指導方針，您必須與合作夥伴聯繫，以進一步疑難排解。 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell for Cloud Video Interop

您可以使用下列 PowerShell Cmdlet 來 (部分) 雲端視像交互操作部署。

- **Get-CsTeamsVideoInteropServicepolicy：Microsoft** 會針對每個支援的合作夥伴提供預先建構的策略，讓您指定要用於雲端視訊交互 () 的合作夥伴。<br>此 Cmdlet 可讓您識別可在貴組織中使用的預先建構策略。 您可以使用 Cmdlet，將這個Grant-CsTeamsVideoInteropServicePolicy指派給一Grant-CsTeamsVideoInteropServicePolicy使用者。
- **Grant-CsTeamsVideoInteropServicePolicy：** 此 Cmdlet 可讓您指派預先建構的策略，供貴組織使用，或將策略指派給特定使用者。
- **New-CsVideoInteropServiceProvider：** 使用此 Cmdlet 來指定貴組織想使用之支援的 CVI 合作夥伴相關資訊。
- **Set-CsVideoInteropServiceProvider：** 使用此 Cmdlet 更新貴組織使用之支援的 CVI 合作夥伴相關資訊。
- **Get-CsVideoInteropServiceProvider：** 使用此 Cmdlet 取得組織中所有已配置的提供者。
- **Remove-CsVideoInteropServiceProvider：** 使用此 Cmdlet 移除貴組織不再使用之提供者的所有提供者資訊。