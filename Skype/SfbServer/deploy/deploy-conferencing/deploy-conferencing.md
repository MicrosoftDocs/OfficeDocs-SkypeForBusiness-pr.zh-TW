---
title: 在商務用 Skype Server 中部署會議
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26dff7d8-242a-4576-9870-d6d461758a37
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 中部署會議。
ms.openlocfilehash: 85aa9b28ddcc262ae65700e0b0425ebec3dd0d12
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599538"
---
# <a name="deploy-conferencing-in-skype-for-business-server"></a>在商務用 Skype Server 中部署會議

**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 中部署會議。

商務用 Skype Server 有四種會議類型： web 會議、音訊和影片 (A/V) 會議、電話撥入式會議和立即訊息 (IM) 會議。 您可以選擇啟用所有會議類型，或根據您的需求，只使用一種類型。

當您部署商務用 Skype Server 時，會自動部署 IM 會議功能。 當您使用拓撲產生器建立及發行新的拓撲時，您可以指定是否要部署 web、A/V 和電話撥入式會議，如下列檢查清單所述：

- [Web 和音訊/視訊會議的部署檢查清單](deploy-conferencing.md#BKMK_ChecklistWebConferencing)

- [電話撥入式會議的部署流程圖及檢查清單](deploy-conferencing.md#BKMK_DialinConferencing)

在您部署會議之前，您應該閱讀下列規劃主題：

- [在商務用 Skype Server 中規劃會議](../../plan-your-deployment/conferencing/conferencing.md)

- [商務用 Skype Server 中會議的硬體和軟體需求](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)

- [規劃商務用 Skype Server 的會議拓撲](../../plan-your-deployment/conferencing/conferencing-topology.md)

- [規劃商務用 Skype Server 中的電話撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md)

- [在商務用 Skype Server 中規劃大型會議](../../plan-your-deployment/conferencing/large-meetings.md)

## <a name="deployment-checklist-for-web-and-audiovideo-conferencing"></a>Web 和音訊/視訊會議的部署檢查清單
<a name="BKMK_ChecklistWebConferencing"> </a>

下表提供在現有拓撲中部署 web 和音訊/視訊會議所需步驟的概述。 包含相關聯的規劃和程式檔的連結。

|**階段**|**步驟**|**角色和群組成員資格**|**文件**|
|:-----|:-----|:-----|:-----|
|**安裝必要的硬體和軟體** <br/> |會議會在前端集區和 Standard Edition 伺服器的前端伺服器上執行。 請參閱前端伺服器的伺服器及環境需求。  <br/> 如果您要啟用 web 會議，則必須確定商務用 Skype Server 可以與 Office web Apps Server 通訊，以用於處理 PowerPoint 簡報的共用及呈現。  <br/> 若為 web 會議，您也必須指定要用來做為檔案存放區的檔案共用。  <br/> 您是否要讓具有商務用 Skype 用戶端的外部使用者加入會議？ 如果是的話，您必須部署 Edge Server。  <br/> |為本機系統管理員成員之網域使用者  <br/> | [商務用 Skype Server 2019 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md) <br> [商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [商務用 Skype Server 2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [商務用 Skype Server 中會議的硬體和軟體需求](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [設定商務用 Skype Server 中的 Office Web 應用程式伺服器的整合](office-web-app-server.md) <br/> [在商務用 Skype Server 中建立檔案共用](../../deploy/install/create-a-file-share.md) <br/> [規劃商務用 Skype Server 2015 中的 Edge Server 部署](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) <br/> [在商務用 Skype Server 2015 中部署 Edge Server](../../deploy/deploy-edge-server/deploy-edge-server.md) <br/> |
|**建立適當的內部拓撲以支援會議** <br/> |您必須執行拓撲產生器，才能將會議新增至拓撲，然後發行拓撲。  <br/> |定義拓撲，須以本機使用者群組成員帳戶進行  <br/> 若要發行拓撲，您必須是 Domain Admins 群組成員和 RTCUniversalServerAdmins 群組成員的帳戶，且具有商務用 Skype Server 檔案存放區之檔案共用上的「讀取/寫入/修改」) 的「完全控制」許可權 (可供拓撲產生器設定所需的 dacl (  <br/> |[在商務用 Skype Server 中建立及發行新的拓撲](../../deploy/install/create-and-publish-new-topology.md) <br/> |
|**設定會議原則及設定設定** <br/> |使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面，設定會議原則及設定設定。  <br/> |RTCUniversalServerAdmins 群組 (Windows PowerShell 只) 或指派使用者至 CSAdministrator 角色  <br/> |[在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md) <br/> [在商務用 Skype Server 中管理會議配置設定](../../manage/conferencing/meeting-configuration-settings.md) <br/> [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> [New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> [Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |

## <a name="deployment-flowchart-and-checklist-for-dial-in-conferencing"></a>電話撥入式會議的部署流程圖及檢查清單
<a name="BKMK_DialinConferencing"> </a>

 電話撥入式會議可讓使用者從公用交換電話網路 (PSTN) 撥號，以加入音訊/視訊會議。

電話撥入式會議所需的部分元件也會用於企業語音。 例如，如果您要部署企業語音，也必須部署轉送伺服器和 PSTN 閘道，也就是電話撥入式會議所需的元件。 部署電話撥入式會議的方式，取決於您是否也部署企業語音解決方案。

電話撥入式會議流程圖顯示您必須遵循的步驟，取決於您是否也要部署企業語音解決方案。 流程圖後的表格提供部署電話撥入式會議所需的步驟和建議步驟的概述。 此外，也包含相關規劃與程式檔的連結。 如需規劃完整企業語音解決方案的詳細資訊，請參閱[商務用 Skype Server 中的規劃企業語音解決方案](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)。

**電話撥入式會議流程圖**

![部署電話撥入式會議流程圖流程圖表](../../media/95d2f963-7705-4930-90bc-df6a71a700bf.png)

**電話撥入式會議部署檢查清單**

|**階段**|**步驟**|**角色和群組成員資格**|**文件**|
|:-----|:-----|:-----|:-----|
|**安裝必要的硬體和軟體** <br/> | 會議會在前端集區和 Standard Edition 伺服器的前端伺服器上執行。 請參閱前端伺服器的伺服器及環境需求。 <br/>  在設定電話撥入式會議之前，您必須先確定已安裝下列專案： <br/>  中繼伺服器 <br/>  PSTN 閘道 <br/>  整合通訊應用程式服務 (UCAS)  (稱為 Application Service)  <br/>  Conferencing Attendant application <br/>  Conferencing Announcement application <br/> |為本機系統管理員成員之網域使用者  <br/> |[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [商務用 Skype Server 2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [商務用 Skype Server 中會議的硬體和軟體需求](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [規劃商務用 Skype Server 中的電話撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md) <br/> [商務用 Skype Server 中的轉送伺服器元件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) <br/> [在商務用 Skype Server 中的拓撲產生器中部署轉送伺服器](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [在商務用 Skype Server 中定義拓撲產生器中的閘道](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**建立包含會議工作負載的拓撲，包括轉送伺服器和 PSTN 閘道，以及部署前端集區或 Standard Edition 伺服器** <br/> |1. 執行拓撲產生器以設定拓撲。 設定拓撲時，請選取 [電話撥入式會議] 選項。  <br/> 2. 發佈拓撲，並部署前端集區或 Standard Edition 伺服器。  <br/> 3. 如有必要，請建立獨立的轉送伺服器，並將它與 PSTN 閘道產生關聯。  <br/> **附注：** 只有在您未部署企業語音，但未使用 Enterprise Edition 前端伺服器或 Standard Edition 伺服器組合轉送伺服器時，才需要此步驟。 如果您要部署企業語音，您可以在企業語音部署中安裝及設定轉送伺服器和 PSTN 閘道。 如果您組合轉送伺服器，請在前端集區或 Standard Edition 伺服器部署中安裝及設定轉送伺服器。 <br/> |Domain Admins  <br/> RTCUniversalServerAdmins  <br/> 系統管理員  <br/> |[在商務用 Skype Server 中建立及發行新的拓撲](../../deploy/install/create-and-publish-new-topology.md) <br/> [在商務用 Skype Server 中的拓撲產生器中部署轉送伺服器](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [在商務用 Skype Server 中定義拓撲產生器中的閘道](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**設定撥號對應表** <br/> |撥號對應表是一組電話號碼正規化規則，可將從特定位置撥打的電話號碼，轉譯成單一標準 () 格式，以進行電話授權和呼叫路由的目的。 從不同位置撥打的相同電話號碼可以根據各自的撥號對應表，視各自的位置而定，解析為不同的 e.164 號碼。 如果您部署企業語音，您可以將撥號對應表設定為該部署的一部分，而且您必須確定撥號對應表也能容納電話撥入式會議。 如果您未部署企業語音，您必須設定電話撥入式會議的撥號對應表。  <br/> 使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面設定撥號對應表，如下所示：  <br/> 1. 建立一或多個用於路由撥入存取電話號碼的撥號對應表。  <br/> 2. 將預設的撥號對應表指派給每個集區。 將 **電話撥入式會議地區** 設定為套用撥號對應表的地理位置。 地區會將撥號對應表與電話撥入存取號碼產生關聯。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中設定電話撥入式會議](dial-in-conferencing.md) <br/> [在商務用 Skype Server 中建立或修改撥號對應表](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [新 Get-csdialplan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |
|**請確定已將撥號對應表指派給地區** <br/> |請執行 **Get-CsDialPlan** 和 **Set-CsDialPlan** Cmdlet，以確定所有撥號對應表均已指派地區。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中設定電話撥入式會議](dial-in-conferencing.md) <br/> [在商務用 Skype Server 中建立或修改撥號對應表](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> [Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |
|**設定會議原則以支援電話撥入式會議** <br/> | 使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面設定 **會議原則** 設定。 指定： <br/>  已啟用 PSTN 會議撥入功能。 <br/>  使用者可以邀請匿名參與者。 <br/>  未驗證的使用者可以使用撥出 phoning 加入會議。 透過撥出 phoning，會議服務器呼叫使用者，而使用者接聽電話以加入會議。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md) <br/> [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |
|**設定撥入存取號碼** <br/> |使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面來設定使用者撥打至會議的撥入存取號碼，並指定與適當撥號對應表相關聯之存取號碼的地區。 召集人的撥號對應表所指定之區域的前三個存取號碼會包含在會議邀請中。 所有的存取號碼均可在 [電話撥入式會議設定] 頁面上。  <br/> **附注：** 建立撥入存取號碼之後，您可以使用 **Set-CsDialInConferencingAccessNumber** Cmdlet 來修改 Active Directory 連絡人物件的顯示名稱，這樣使用者就能更輕鬆地識別正確的存取號碼。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中建立或修改撥號對應表](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [管理商務用 Skype Server 中的電話撥入式會議存取號碼](../../manage/conferencing/access-numbers.md) <br/> [New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**將行 URI 指派給使用者帳戶** <br/> |使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面，將電話語音列 **URI** 設定為唯一且正規化的電話號碼 (例如電話： + 14255550200) 。 <br/> |RTCUniversalServerAdmins  <br/> CsAdministrator  <br/> CsUserAdministrator  <br/> |[將行 URI 指派給使用者帳戶](dial-in-conferencing.md#BKMK_AssignaLineURI) <br/> |
|**(選用) 驗證或修改使用者個人身分識別號碼 (PIN) 需求** <br/> |使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面，以查看或修改會議 **PIN 原則**。 您可以指定最小 PIN 碼長度、登入嘗試次數上限、PIN 碼到期，以及是否允許通用模式。  <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則](../../manage/conferencing/pin-policies.md) <br/> [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |
|**(選用) Modify DTMF 命令的按鍵對應** <br/> |您可以使用 **Set-CsDialinConferencingDtmfConfiguration** Cmdlet，修改雙音調多重頻率 (DTMF) 命令所用的按鍵，讓參與者可用來控制會議設定 (例如靜音和取消靜音或鎖定和解除鎖定) 。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中管理 DTMF 命令的按鍵對應](../../manage/conferencing/key-mapping-for-dtmf-commands.md) <br/> [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |
|**(選用) Modify 會議加入和離開宣告行為** <br/> |使用 **Set-CsDialinConferencingConfiguration** 變更參與者加入和離開會議時的宣告運作方式。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中管理會議加入和離開宣告](../../manage/conferencing/join-and-leave-announcements.md) <br/> [CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |
|**(建議) 設定會議目錄** <br/> |使用 **New-CsConferenceDirectory** Cmdlet 為集區中的每個999使用者建立一個會議目錄。 <br/> |RTCUniversalServerAdmins  <br/> |[ (建議) 建立會議目錄](/previous-versions/office/lync-server-2013/recommended-create-conference-directories) <br/> [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |
|**(選用) 驗證電話撥入式會議設定** <br/> |使用 **Get-CsDialinConferencingAccessNumber** 指令程式來搜尋撥號對應表，其中含有未獲任何存取號碼及未指派任何區域之電話撥入式會議區域的撥號對應表。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> CsHelpDesk  <br/> |[在商務用 Skype Server 中設定電話撥入式會議](dial-in-conferencing.md) <br/> [測試商務用 Skype Server 中的電話撥入式會議](../../manage/conferencing/tests.md) <br/> [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**(選用) 驗證電話撥入式會議** <br/> |使用 **Test-CsDialInConferencing** Cmdlet 來測試指定集區的存取號碼是否運作正常。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[測試商務用 Skype Server 中的電話撥入式會議](../../manage/conferencing/tests.md) <br/> [Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |
|**(選用) 歡迎使用者的電話撥入式會議和設定初始 PIN 碼** <br/> |使用 **Set-CsPinSendCAWelcomeMail** 腳本來設定使用者的初始 pin，並傳送包含初始 PIN 的歡迎電子郵件，以及電話撥入式會議設定] 頁面的連結。 <br/> |RTCUniversalServerAdmins  <br/> |[將歡迎電子郵件傳送至商務用 Skype Server 中的撥入使用者](../../manage/conferencing/welcome-emails.md) <br/> |