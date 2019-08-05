---
title: 在商務用 Skype Server 中部署會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26dff7d8-242a-4576-9870-d6d461758a37
description: '摘要: 請閱讀本主題, 以瞭解如何在商務用 Skype Server 中部署會議。'
ms.openlocfilehash: 08cdf52815b7a3ce2b768520f269abfa4be41279
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187537"
---
# <a name="deploy-conferencing-in-skype-for-business-server"></a>在商務用 Skype Server 中部署會議

**摘要:** 若要瞭解如何在商務用 Skype Server 中部署會議, 請閱讀本主題。

商務用 Skype Server 中提供了四種會議類型: 網路會議、音訊與影片 (A/V) 會議、電話撥入式會議, 以及立即訊息 (IM) 會議。 根據您的需求, 您可以選擇啟用所有會議類型, 或只使用一種類型。

當您部署商務用 Skype Server 時, IM 會議功能會自動部署。 當您使用 [拓撲建立器] 建立併發布新的拓撲時, 請指定是否要部署 web、A/V 和電話撥入式會議, 如下列檢查清單所述:

- [網路和音訊/視訊會議的部署檢查清單](deploy-conferencing.md#BKMK_ChecklistWebConferencing)

- [電話撥入式會議的部署流程圖與檢查清單](deploy-conferencing.md#BKMK_DialinConferencing)

在您部署會議之前, 您應該閱讀下列規劃主題:

- [在商務用 Skype Server 中規劃會議](../../plan-your-deployment/conferencing/conferencing.md)

- [商務用 Skype Server 中的會議硬體和軟體需求](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)

- [規劃商務用 Skype Server 的會議拓撲](../../plan-your-deployment/conferencing/conferencing-topology.md)

- [在商務用 Skype Server 中規劃電話撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md)

- [在商務用 Skype Server 中規劃大型會議](../../plan-your-deployment/conferencing/large-meetings.md)

## <a name="deployment-checklist-for-web-and-audiovideo-conferencing"></a>網路和音訊/視訊會議的部署檢查清單
<a name="BKMK_ChecklistWebConferencing"> </a>

下表提供將 web 和音訊/視訊會議部署到現有拓撲中所需步驟的概覽。 隨附相關規劃與程式化檔的連結。

|**分**|**步驟**|**角色和群組成員資格**|**文件**|
|:-----|:-----|:-----|:-----|
|**安裝必要的硬體和軟體** <br/> |會議會在前端池和標準版伺服器的前端伺服器上執行。 請參閱前端伺服器的伺服器和環境需求。  <br/> 如果您要啟用 web 會議, 您將需要確保商務用 Skype 伺服器可以與 Office Web Apps 伺服器通訊, 以處理 PowerPoint 簡報的共用和轉譯。  <br/> 針對網路會議, 您也需要指定要用來做為檔案存放區的檔案共用。  <br/> 您想要讓使用商務用 Skype 用戶端的外部使用者加入會議嗎？ 如果是這樣, 您必須部署邊緣伺服器。  <br/> |屬於本機管理員群組成員的網域使用者  <br/> | [商務用 Skype Server 2019 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md) <br> [商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [商務用 Skype Server 2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [商務用 Skype Server 中的會議硬體和軟體需求](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [在商務用 Skype Server 中設定與 Office Web Apps Server 的整合](office-web-app-server.md) <br/> [在商務用 Skype Server 中建立檔案共用](../../deploy/install/create-a-file-share.md) <br/> [在商務用 Skype Server 2015 中規劃 Edge 伺服器部署](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) <br/> [在商務用 Skype Server 2015 中部署 Edge 伺服器](../../deploy/deploy-edge-server/deploy-edge-server.md) <br/> |
|**建立適當的內部拓朴以支援會議** <br/> |您必須執行拓撲建立器, 才能新增會議到拓撲結構, 然後發佈拓撲。  <br/> |若要定義拓撲, 該帳戶是 [本機使用者] 群組的成員  <br/> 若要發佈拓朴, 該帳戶是網域系統管理員群組和 RTCUniversalServerAdmins 群組的成員, 且在檔案共用上具有完全控制許可權 (讀取/寫入/修改), 以用於商務用 Skype Server 檔存放區 (如此一來, 該拓撲Builder 可以設定所需的 Dacl)  <br/> |[在商務用 Skype Server 中建立和發佈新的拓撲](../../deploy/install/create-and-publish-new-topology.md) <br/> |
|**設定會議原則和設定設定** <br/> |使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理命令介面] 來設定會議原則和設定設定。  <br/> |RTCUniversalServerAdmins 群組 (僅限 Windows PowerShell) 或將使用者指派給 CSAdministrator 角色  <br/> |[在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md) <br/> [在商務用 Skype Server 中管理會議設定設定](../../manage/conferencing/meeting-configuration-settings.md) <br/> [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> [New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |

## <a name="deployment-flowchart-and-checklist-for-dial-in-conferencing"></a>電話撥入式會議的部署流程圖與檢查清單
<a name="BKMK_DialinConferencing"> </a>

 電話撥入式會議可讓使用者從公用的交換電話網絡 (PSTN) 撥入, 以加入音訊/視訊會議。

電話撥入式會議所需的部分元件也適用于企業語音。 例如, 如果您要部署企業語音, 您也必須部署一個中繼伺服器和 PSTN 閘道, 也就是電話撥入式會議所需的元件。 您部署電話撥入式會議的方式, 取決於您是否也要部署企業語音方案。

[電話撥入式會議流程圖] 會根據您是否也要部署企業語音解決方案, 顯示您必須遵循的步驟。 流程圖後的表格提供部署電話撥入式會議所需步驟及建議的步驟概覽。 相關的規劃與程式檔的連結也會包含在其中。 如需規劃完整企業語音解決方案的詳細資訊, 請參閱[規劃商務用 Skype Server 中的企業語音方案](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)。

**電話撥入式會議流程圖**

![部署電話撥入式會議流程圖](../../media/95d2f963-7705-4930-90bc-df6a71a700bf.png)

**電話撥入式會議部署檢查清單**

|**分**|**步驟**|**角色與群組成員資格**|**文件**|
|:-----|:-----|:-----|:-----|
|**安裝必要的硬體和軟體** <br/> | 會議會在前端池和標準版伺服器的前端伺服器上執行。 請參閱前端伺服器的伺服器和環境需求。 <br/>  設定電話撥入式會議之前, 您必須先確認已安裝下列各項: <br/>  中繼伺服器 <br/>  PSTN 閘道 <br/>  整合通訊應用程式服務 (UCAS) (稱為應用程式服務) <br/>  會議助理應用程式 <br/>  會議公告應用程式 <br/> |屬於本機管理員群組成員的網域使用者  <br/> |[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [商務用 Skype Server 2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [商務用 Skype Server 中的會議硬體和軟體需求](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [在商務用 Skype Server 中規劃電話撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md) <br/> [商務用 Skype Server 中的中繼伺服器元件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) <br/> [在商務用 Skype Server 的 [拓撲產生器] 中部署轉送伺服器](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [在商務用 Skype Server 的 [拓撲 Builder] 中定義閘道](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**建立包含會議工作負載的拓撲, 包括轉送伺服器和 PSTN 閘道, 以及部署前端池或標準版伺服器** <br/> |1. 執行拓撲產生器以設定您的拓撲。 配置拓撲時, 請選取 [電話撥入式會議] 選項。  <br/> 2. 發佈拓撲並部署前端池或標準版伺服器。  <br/> 3. 如有必要, 請建立獨立的中繼伺服器, 並將它與 PSTN 閘道建立關聯。  <br/> **注意:** 只有當您不部署企業語音, 且不 collocate 使用企業版前端伺服器或標準版伺服器的中繼伺服器時, 才需要執行此步驟。 如果您要部署企業語音, 您必須安裝並設定轉送伺服器和 PSTN 閘道, 做為企業語音部署的一部分。 如果您 collocate 的是中繼伺服器, 您可以在前端池或標準版伺服器部署中安裝並設定中繼伺服器。 <br/> |網域管理員  <br/> RTCUniversalServerAdmins  <br/> 許可權  <br/> |[在商務用 Skype Server 中建立和發佈新的拓撲](../../deploy/install/create-and-publish-new-topology.md) <br/> [在商務用 Skype Server 的 [拓撲產生器] 中部署轉送伺服器](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [在商務用 Skype Server 的 [拓撲 Builder] 中定義閘道](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**設定撥號方案** <br/> |撥號方案是一組電話號碼正規化規則, 可將從特定位置撥打電話的電話號碼轉換為單一標準 (e. 164) 格式, 以用於手機授權及呼叫路由。 根據各自的撥號方案, 從不同位置撥打電話的電話號碼, 視每個地點適當地解析成不同的 e. 164 號碼。 如果您要部署企業語音, 請將撥號方案設定為該部署的一部分, 而且您必須確認撥號方案也能容納電話撥入式會議。 如果您沒有部署企業語音, 您必須為電話撥入式會議設定撥號方案。  <br/> 使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理命令介面] 來設定撥號方案, 如下所示:  <br/> 1. 建立一或多個用來傳送撥入存取電話號碼的撥號方案。  <br/> 2. 將預設撥號方案指派給每個池。 將**電話撥入式會議區域**設定為要套用撥號計畫的地理位置。 該區域會將撥號方案與撥入存取號碼進行關聯。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中設定電話撥入式會議](dial-in-conferencing.md) <br/> [在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [新-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |
|**確定撥號方案是指派的區域** <br/> |執行**CsDialPlan**和**CsDialPlan** Cmdlet, 以確定所有撥號方案都已指派區域。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中設定電話撥入式會議](dial-in-conferencing.md) <br/> [在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |
|**設定會議原則以支援電話撥入式會議** <br/> | 使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理命令介面] 來設定**會議原則**設定。 指定是否: <br/>  已啟用 PSTN 會議撥入。 <br/>  使用者可以邀請匿名參與者。 <br/>  未經驗證的使用者可以使用撥出 phoning 加入會議。 使用撥出 phoning, 會議服務器就會呼叫使用者, 而使用者會接聽電話加入會議。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md) <br/> [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |
|**設定撥入存取號碼** <br/> |使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理] 命令介面, 以設定使用者撥入會議所撥打的撥入號碼, 並指定將存取號碼與適當的撥號方案相關聯的地區。 召集人撥號計畫所指定之區域的前三個存取號碼包含在會議邀請中。 [電話撥入式會議設定] 頁面上提供所有存取號碼。  <br/> **注意:** 在您建立撥入存取號碼之後, 您可以使用**CsDialInConferencingAccessNumber** Cmdlet 來修改 Active Directory 連絡人物件的顯示名稱, 讓使用者能更輕鬆地識別正確的存取號碼。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [管理商務用 Skype Server 中的電話撥入式會議存取號碼](../../manage/conferencing/access-numbers.md) <br/> [新-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**將行 URI 指派給使用者帳戶** <br/> |使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理命令介面], 將電話**線路 URI**設定為唯一、標準化的電話號碼 (例如電話: + 14255550200)。 <br/> |RTCUniversalServerAdmins  <br/> CsAdministrator  <br/> CsUserAdministrator  <br/> |[將行 URI 指派給使用者帳戶](dial-in-conferencing.md#BKMK_AssignaLineURI) <br/> |
|**可選驗證或修改使用者個人識別碼 (PIN) 需求** <br/> |使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理命令介面] 來查看或修改會議**PIN 原則**。 您可以指定最小 PIN 長度、最大登入嘗試次數、PIN 到期日, 以及是否允許通用模式。  <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則](../../manage/conferencing/pin-policies.md) <br/> [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |
|**可選修改 DTMF 命令的金鑰組應** <br/> |使用**CsDialinConferencingDtmfConfiguration** Cmdlet 來修改雙音調多頻率 (DTMF) 命令所使用的金鑰, 參與者可以用來控制會議設定 (例如靜音和取消靜音, 或鎖定與解除鎖定)。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中管理 DTMF 命令的金鑰組應](../../manage/conferencing/key-mapping-for-dtmf-commands.md) <br/> [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |
|**可選修改會議加入並離開宣告行為** <br/> |使用**CsDialinConferencingConfiguration**變更參與者加入與離開會議時的宣告運作方式。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中管理會議加入與離開宣告](../../manage/conferencing/join-and-leave-announcements.md) <br/> [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |
|**採用設定會議目錄** <br/> |使用**CsConferenceDirectory** Cmdlet 為池中的每個999使用者建立一個會議目錄。 <br/> |RTCUniversalServerAdmins  <br/> |[(建議) 建立會議目錄](https://technet.microsoft.com/library/787f4c94-1c96-468a-a74d-e06b7bd4b8a3.aspx) <br/> [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |
|**(選用) 驗證電話撥入式會議設定** <br/> |使用**CsDialinConferencingAccessNumber** Cmdlet 來搜尋具有電話撥入式會議區域的撥號方案, 這些方案不是由任何存取號碼和沒有指派區域的存取號碼所使用。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> CsHelpDesk  <br/> |[在商務用 Skype Server 中設定電話撥入式會議](dial-in-conferencing.md) <br/> [在商務用 Skype Server 中測試電話撥入式會議](../../manage/conferencing/tests.md) <br/> [CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**(選用) 驗證電話撥入式會議** <br/> |使用**CsDialInConferencing** Cmdlet 來測試指定池的存取號碼是否正常運作。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype Server 中測試電話撥入式會議](../../manage/conferencing/tests.md) <br/> [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |
|**可選歡迎使用者撥入式會議及設定初始 PIN** <br/> |使用**CsPinSendCAWelcomeMail**腳本來設定使用者的初始 pin, 並傳送包含初始 PIN 的歡迎電子郵件, 以及 [電話撥入式會議設定] 頁面的連結。 <br/> |RTCUniversalServerAdmins  <br/> |[在商務用 Skype Server 中傳送歡迎電子郵件給撥入使用者](../../manage/conferencing/welcome-emails.md) <br/> |


