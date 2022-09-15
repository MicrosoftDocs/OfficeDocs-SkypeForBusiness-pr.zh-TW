---
title: Microsoft Teams 雲端視訊 Interop。
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: 使用雲端視訊 Interop 做為中繼解決方案，允許協力廠商會議室裝置加入 Microsoft Teams 會議。
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c732cc01a525a4895fafe45c954c965fe960853
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706450"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams 雲端視訊 Interop。

雲端視訊 Interop (CVI) 是 Microsoft 合格的協力廠商解決方案，可讓協力廠商會議室 () 個人視訊裝置 (VTC) 加入 Microsoft Teams 會議。
 
透過 Microsoft Teams，您可以在會議中獲得豐富的線上內容共同作業，包括音訊、視訊和內容共用。 這可透過桌面和 Web 用戶端，以及透過許多以原生方式與 Microsoft Teams 整合的合作夥伴裝置來享用。 不過，許多客戶已經投資了視頻電話會議和個人視訊通訊裝置，升級費用可能很貴。 雲端視訊 Interop 提供簡單的解決方案，可讓您繼續使用現有的解決方案，直到您準備好升級為止。

透過雲端視訊 Interop，Microsoft Teams 可在會議室或 Teams 用戶端內為所有參與者提供原生會議體驗。

### <a name="is-cloud-video-interop-for-me"></a>雲端視訊是否適合我？

雲端視訊 Interop 提供中繼服務，當您使用 Teams 端點轉換到完整的原生 Microsoft Teams 解決方案時。 提供的服務應為移轉路徑的一部分。

雲端視訊 Interop 適用于符合下列準則的客戶：

-  (50 部以上的裝置部署大型會議室裝置和個人視訊裝置部署，) 不符合與 Microsoft Teams 直接整合的資格
- 我們其中一個雲端視訊 Interop 合作夥伴支援
- 想要在移轉到原生 Microsoft Teams 解決方案期間，保留他們對其目前會議室裝置和個人視訊裝置的投資價值

雖然雲端視訊 Interop 提供絕佳的中繼解決方案，但我們鼓勵客戶長期探討我們原生 Teams 會議解決方案，例如 Teams 會議室系統。 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365美國政府和協力廠商服務

Office 365可讓您將協力廠商應用程式整合至 SharePoint Online 網站、商務用 Skype、Teams、Microsoft 365 Apps 企業版 (中包含的 Office 應用程式，例如 Word、Excel、PowerPoint 和 Outlook) 和 Outlook Web App。 此外，Office 365支援與協力廠商服務提供者整合。 這些協力廠商應用程式和服務可能涉及在Office 365基礎結構以外的協力廠商系統上儲存、傳輸及處理貴組織的客戶資料，因此不在Office 365合規性和資料保護承諾的涵蓋範圍之內。 **建議您在評估貴組織適當使用這些服務時，檢閱協力廠商提供的隱私權與合規性聲明。**



### <a name="partners-certified-for-microsoft-teams"></a>經 Microsoft Teams 認證的合作夥伴

下列合作夥伴提供 Microsoft Teams 的視訊互通解決方案。 貴公司可選擇與企業內的這些合作夥伴合作。 

|夥伴|合作夥伴解決方案|
|----|---|
|![代表 Poly RealConnect 的標誌。](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect 服務</a> |
|![代表 Pexip Infinity 的標誌。](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft Teams 的 Pexip Infinity</a> | 
|![代表 BlueJeans 閘道的標誌。](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft Teams 的 BlueJeans 閘道</a> |
|![代表 Cisco CVI 的標誌。](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration for Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>雲端視訊互通概觀

雲端視訊 Interop 是協力廠商服務，由我們的合作夥伴提供，可在內部部署的現有視訊會議和個人視訊裝置解決方案與 Microsoft Teams 之間提供互通性。

我們的合作夥伴提供的解決方案包含可在內部部署完整雲端或部分/完整內部部署的元件。 
     
下圖顯示我們的合作夥伴解決方案的高層級架構。

![說明 Teams 雲端視訊 Interop 合作夥伴解決方案的圖表。](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>部署雲端視訊 Interop

部署雲端視訊 Interop 解決方案時，請務必瞭解您正在部署合作夥伴解決方案。 下列圖表列出部署雲端視訊 Interop 的一般步驟。

![說明在貴組織中部署 CVI 的圖表。](media/deploying-cvi.png)

### <a name="plan"></a>規劃

在計畫階段期間，您應識別不會以原生 Teams 裝置取代的裝置，並尋找可支援這些裝置的雲端視訊 Interop 合作夥伴。  

另請務必瞭解，您需要授權給每位使用者，並排程您希望使用雲端視訊 Interop 功能的裝置加入的會議。 請注意，您可以從雲端視訊 Interop 合作夥伴取得確切的授權需求。 在開始部署之前，請先確認已清除此設定。

### <a name="configure"></a>配置

您選擇用於 CVI 部署的合作夥伴將提供完整部署檔，其中包含在組織內成功部署所需的所有步驟。 這包括防火牆埠和 IP 範圍、您裝置的設定變更，以及其他需要變更的設定。

### <a name="provision"></a>提供  

在布建階段期間，您將根據合作夥伴設定指南，指派授權給適當的使用者。 您也必須完成 Azure 同意程式，讓合作夥伴可以存取您的 Teams 環境。 如需 Azure 同意程式的詳細資訊，請參閱[Microsoft 身分識別平臺端點中的](/azure/active-directory/develop/v2-permissions-and-consent)許可權與同意。

### <a name="schedule"></a>附表

在使用者啟用雲端視訊 Interop 之後，任何使用 Outlook Teams 會議增益集或 Teams 用戶端排程的會議，都會自動將適當的額外資訊新增至 Teams 會議，讓與雲端視訊互通相容的裝置可以加入這些會議。

### <a name="join"></a>加入

視合作夥伴解決方案而定，有數種方式可以加入支援雲端視訊 Interop 功能的會議。 確切的會議加入案例將由您的雲端視訊 Interop 合作夥伴提供。 我們已在下列列出一些範例：

- IVR (互動式語音回應)  
  - 您可以使用tenantkey@domain撥入合作夥伴的 IVR。
  - 當您在合作夥伴 IVR 中時，系統會提示您輸入 VTC 會議Id，然後將您連線至 Teams 會議。
- 直撥 
  - 您可以直接撥入 Teams 會議，而不需使用直接撥號功能與合作夥伴的 IVR 互動，方法是使用完整的租使用者金鑰字串。VTC ConferenceId@domain。
- 單點觸控轉盤 
  - 如果您有整合的 Teams 會議室，您可以使用合作夥伴 (提供的單點觸控撥號功能，而不需要輸入任何撥號字串) 。

## <a name="manage-cloud-video-interop"></a>管理雲端視訊 Interop

部署雲端視訊 Interop 之後，您可以使用我們的合作夥伴所提供的解決方案來管理裝置。 每個合作夥伴都會提供您一個系統管理介面，其中包含授權和裝置管理。 

報告也可以直接從合作夥伴系統管理介面取得。 如需報告功能的詳細資訊，請連絡您選擇的合作夥伴。 

### <a name="troubleshooting-cloud-video-interop"></a>雲端視訊 Interop 疑難排解

雲端視訊 Interop 是合作夥伴提供的服務。 如果您遇到問題，第一個步驟是連接已安裝 Teams 用戶端的裝置，並將它連線到與造成問題的雲端視訊 Interop 裝置相同的區段。 

如果 Teams 在此區段中正常運作，而且您也遵循了合作夥伴提供的所有網路和設定指導方針，您將需要連絡合作夥伴以進行進一步的疑難排解。 

## <a name="powershell-for-cloud-video-interop"></a>適用于雲端視訊 Interop 的 PowerShell

下列 PowerShell Cmdlet 可供您 (部分) 自動化雲端視訊 Interop 部署。

- **Get-CsTeamsVideoInteropServicepolicy**：Microsoft 為每個支援的合作夥伴提供預先建構的原則，可讓您指定要用於雲端視訊 Interop 的合作夥伴 () 。<br>此 Cmdlet 可讓您識別可在組織中使用的預先建構原則。 您可以利用Grant-CsTeamsVideoInteropServicePolicy Cmdlet，將此原則指派給一或多個使用者。
- **Grant-CsTeamsVideoInteropServicePolicy**：此 Cmdlet 可讓您指派預先建構的原則供組織使用，或將原則指派給特定使用者。
- **New-CsVideoInteropServiceProvider**：使用此 Cmdlet 來指定貴組織想要使用的支援 CVI 合作夥伴的相關資訊。
- **Set-CsVideoInteropServiceProvider**：使用此 Cmdlet 來更新貴組織所使用之受支援的 CVI 合作夥伴的相關資訊。
- **Get-CsVideoInteropServiceProvider**：使用此 Cmdlet 可取得已設定為在組織內使用的所有提供者。
- **Remove-CsVideoInteropServiceProvider**：使用此 Cmdlet 移除貴組織不再使用之提供者的所有提供者資訊。