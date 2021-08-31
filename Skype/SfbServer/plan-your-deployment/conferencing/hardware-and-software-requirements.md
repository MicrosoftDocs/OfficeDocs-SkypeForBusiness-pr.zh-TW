---
title: 商務用 Skype Server 中會議的硬體和軟體需求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 摘要：閱讀此主題以瞭解商務用 Skype Server 中會議的硬體和軟體需求。
ms.openlocfilehash: bfc449abc2e01676a412fc0ead85eeae12aa2610
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733532"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>商務用 Skype Server 中會議的硬體和軟體需求

**摘要：** 閱讀此主題以瞭解商務用 Skype Server 中會議的硬體和軟體需求。

本節說明 web 會議、音訊和影片 (A/V) 會議、電話撥入式會議和立即訊息 (IM) 會議的硬體和軟體需求。 在前端伺服器上執行的所有會議功能;不同會議類型還有其他需求，如下圖所示。

例如，如果您想要允許電話撥入式會議，您需要部署轉送伺服器和閘道，以連接至公用交換電話網路 (PSTN) 。 如果您想要允許 web 會議，您必須確定商務用 Skype Server 可以連線到 Office web Apps Server。 如果您想要允許外部使用者參與會議，您需要部署 Edge Server。

**會議功能和需求**

![會議元件。](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 如需拓撲考慮的相關資訊，請參閱[規劃商務用 Skype Server 的會議拓撲](conferencing-topology.md)。

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>前端伺服器的硬體和軟體需求

由於 web 會議、A/V 會議、電話撥入式會議和 IM 會議全都與前端伺服器組合，因此伺服器硬體和軟體需求與前端伺服器相同。 如需這些需求的詳細資訊，請參閱[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)，以及商務用 Skype Server 2019 商務用 Skype Server 2015 或[伺服器需求](../../../SfBServer2019/plan/system-requirements.md)的[環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。

## <a name="requirements-for-web-conferencing"></a>Web 會議的需求

如果您已選擇要啟用 Web 會議，則需規劃下列事項：

- 存取檔案存放區，以用來儲存 Web 會議內容。

- 與 Office 網頁應用程式伺服器整合，以便在會議期間共用 PowerPoint 檔案。

### <a name="file-store"></a>檔案存放區

商務用 Skype Server web 會議服務會儲存在檔存放區中的會議期間共用的內容。 在部署過程中，您必須指定要用來做為 Standard Edition server 或 Enterprise Edition 前端集區之檔案存放區的檔案共用。 您可以使用檔案存放區的現有檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。 如需詳細資訊，請參閱[Create a file share in 商務用 Skype Server](../../deploy/install/create-a-file-share.md)。 Web 會議服務會先對內容進行加密，然後才會將內容儲存在檔案存放區中。

商務用 Skype Server 支援在直接連接儲存區 (DAS) 或儲存區域網路 (SAN) （包括分散式檔案系統 (DFS) ）和獨立磁片冗餘數組（例如檔案存放區的 RAID (）上使用檔案共用。 商務用 Skype Server 部署嚮導定義檔案共用的位置之後，商務用 Skype Server 會在檔案共用中建立資料夾結構，類似下列所示：

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

然後 Web 會議服務會將 PowerPoint 投影片、白板、輪詢及附件之類的內容，儲存在 CollabContent 和 CollabMetadata 資料夾中 (位在 WebServices 資料夾中)。

### <a name="office-web-apps-server"></a>Office Web Apps Server

若要使用 web 會議功能，您必須安裝 Office 網頁應用程式伺服器，並設定商務用 Skype Server 以與 Office 網頁應用程式伺服器進行通訊。

OfficeWeb 應用程式伺服器應該安裝在未執行商務用 Skype Server、SQL Server 或任何其他伺服器應用程式的獨立電腦上。  (您不得在該電腦上安裝任何版本的 Office。 ) 執行 Office Web Apps Server 的任何電腦也必須安裝一組特定的軟體， (包括 .NET Framework 4.5 和 Windows PowerShell 3.0) 。 這些需求，以及設定憑證和 Internet Information Services (IIS) 的相關資訊，會在[Microsoft Office Web Apps 部署網站](/webappsserver/deploy-the-infrastructure-office-web-apps-server)中詳細討論。

如需如何設定商務用 Skype Server 以使用 Office 網頁應用程式伺服器的詳細資訊，請參閱[configure with Office Web apps server in 商務用 Skype Server](../../deploy/deploy-conferencing/office-web-app-server.md)。

## <a name="requirements-for-audio-and-video-conferencing"></a>音訊和視訊會議的需求

若要規劃 A/V 會議，您需要了解組織需要的會議媒體類型及其所需的網路頻寬。 這可能包括音訊、影片及全景影片。 若沒有足夠的網路頻寬，使用者體驗可能會嚴重降低。

如需有關會議之音訊和影片容量規劃的詳細資訊，請參閱[規劃網路需求商務用 Skype](../../plan-your-deployment/network-requirements/network-requirements.md)。

您可以使用 [通話許可控制] (CAC) 管理 A/V 會議所使用的網路頻寬。 這對限制網路很重要，例如中央和分支網站之間有限的頻寬連結。 如需詳細資訊，請參閱[商務用 Skype Server 中的計畫通話許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。

如果您在網路中部署音訊會議，您的使用者將需要諸如耳機等音訊裝置參加音訊會議。 如果您部署了影片會議，您必須部署影片裝置，例如使用者的網路攝像機。 針對音訊和影片裝置，裝置部署和使用者訓練為您考慮考慮的重要步驟。 如需詳細資訊，請參閱 [規劃用戶端和裝置](../../plan-your-deployment/clients-and-devices/clients-and-devices.md)。 Microsoft 建議您針對所有的裝置類型，針對由 Microsoft 認證的 UC) 裝置，使用整合通訊 (，以確保最佳的使用者體驗。 如需 UC 驗證裝置的詳細資訊，請參閱[電話和裝置商務用 Skype](../../../SfbPartnerCertification/certification/devices-ip-phones.md)。

## <a name="requirements-for-dial-in-conferencing"></a>電話撥入式會議的需求

電話撥入式會議是商務用 Skype Server 會議工作負載中包含各種元件的選用功能。 有些元件是電話撥入式會議所特有的，有些則是企業語音元件。 本節說明電話撥入式會議所需元件的需求。 如需有關轉送伺服器和公用交換電話網路 (PSTN) 閘道需求的詳細資訊，請參閱商務用 Skype Server 中的中繼[伺服器元件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)，以及在商務用 Skype Server 的拓撲產生器中[部署轉送伺服器](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)。

### <a name="required-components"></a>必要元件

您必須先安裝下列商務用 Skype Server 元件，才能設定電話撥入式會議：

- 整合通訊應用程式服務 (UCAS)  (稱為 Application Service) 

- Conferencing Attendant application

- Conferencing Announcement application

- 電話撥入式會議設定網頁

- 至少一個轉送伺服器和至少一個 PSTN 閘道

電話撥入式會議、應用程式服務、會議語音應答應用程式和會議宣告應用程式與前端伺服器具有相同的作業系統需求。 如需詳細資訊，請參閱[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。

會議語音應答應用程式和會議宣告應用程式需要在前端伺服器上安裝 Windows 媒體格式執行時間。 Windowsmedia Format Runtime 是播放 Windows 媒體音訊 (WMA) 檔案，以用於等候音樂、錄製名稱及提示。 如果您是在 Windows Server 2012 或 Windows Server 2012 R2 (建議) ，您必須安裝 Microsoft Media Foundation 以取得 Windows 媒體格式執行時間。 若要在 2012 Windows 之前安裝在任何版本的 Windows Server 上，您必須確定已安裝 Windows 的桌面體驗，才能取得 Windows 媒體格式執行時間。

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>電話撥入式會議的音訊檔需求

商務用 Skype Server 不支援自訂語音提示和音樂的電話撥入式會議。 不過，如果您的業務需求很強，需要變更預設的音訊檔，請參閱 Microsoft 知識庫文章961177： [如何自訂語音提示或音樂檔以進行電話語音會議](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)。

您也可以使用[Microsoft Lync Server 會議語音應答自訂語音提示](https://go.microsoft.com/fwlink/p/?LinkId=396880)管理公用程式，讓系統管理員可以取代當電話來電者加入具有自訂提示的商務用 Skype 會議，以提供不同會議輸入經驗時所使用的預設語音提示。 自訂語音提示可以安裝在 Enterprise 或 Standard Edition 伺服器上。

會議語音應答應用程式和會議宣告應用程式對等候音樂、錄製名稱和音訊提示檔有下列需求：

- Windows Media Audio (WMA) 檔案格式

- 16 位元單聲道

- 48 kbps 2-pass CBR (常數位元速率)

- 語音層級為 -24DB

### <a name="user-requirements-for-dial-in-conferencing"></a>電話撥入式會議的使用者需求

必須指派唯一的電話號碼或分機至電話撥入式會議使用者的帳戶。 此需求可支援電話撥入式會議期間的驗證。 Enterprise 使用者 (也就是在組織內具有 Active Directory 網域服務認證和商務用 Skype Server 帳戶的使用者) 輸入其電話號碼 (或分機) ，以及個人識別碼 (PIN) ，以驗證的使用者的身分撥打會議。

## <a name="port-requirements-for-conferencing"></a>會議的埠需求

商務用 Skype Server 需要開啟特定埠才能使用會議功能。 下表列出會議的埠需求。 如需所有埠需求的詳細資訊，請參閱 [伺服器的埠與通訊協定需求](../../plan-your-deployment/network-requirements/ports-and-protocols.md)。

**必要的伺服器埠**


|**伺服器角色**|**服務名稱**|**Port**|**Protocol** (通訊協定)|**附註**|
|:-----|:-----|:-----|:-----|:-----|
|前端伺服器  <br/> |商務用 Skype ServerIM 會議服務  <br/> |5062  <br/> |TCP  <br/> |用於立即訊息 (IM) 會議的傳入 SIP 要求。  <br/> |
|前端伺服器  <br/> |商務用 Skype ServerWeb 會議服務  <br/> |8057  <br/> |TCP (TLS)   <br/> |用於聆聽持續性共用物件模型 (PSOM) 來自用戶端的連線。  <br/> |
|前端伺服器  <br/> |商務用 Skype ServerWeb 會議相容性服務  <br/> |8058  <br/> |TCP (TLS)   <br/> |用於聆聽持續性共用物件模型 (PSOM) 即時會議用戶端和舊版商務用 Skype Server 的連線。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server會議服務 Audio/Video  <br/> |5063  <br/> |TCP  <br/> |用於音訊/視頻 (A/V) 會議的傳入 SIP 要求。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server會議服務 Audio/Video  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |用於視訊會議的媒體埠範圍。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server 會議語音應答服務 (電話撥入式會議)   <br/> |5064  <br/> |TCP  <br/> |用於電話撥入式會議的傳入 SIP 要求。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server 會議語音應答服務 (電話撥入式會議)   <br/> |5072  <br/> |TCP  <br/> |用於在會議) 中傳入的 SIP 要求 (撥號語音應答。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server應用程式共用服務  <br/> |5065  <br/> |TCP  <br/> |用於應用程式共用的傳入 SIP 聆聽要求。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server應用程式共用服務  <br/> |49152-65535  <br/> |TCP  <br/> |用於應用程式共用的媒體埠範圍。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server 會議宣告服務  <br/> |5073  <br/> |TCP  <br/> |用於商務用 Skype Server 會議宣告服務的傳入 SIP 要求 (也就是用於電話撥入式會議) 。  <br/> |
|所有內部伺服器  <br/> |各種  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |用於所有內部伺服器的音訊會議的媒體埠範圍。 由終止音訊的所有伺服器使用：前端伺服器 (商務用 Skype Server 會議語音應答服務、商務用 Skype Server 會議宣告服務，以及商務用 Skype Server Audio/Video 會議服務) 和轉送伺服器。  <br/> |
|OfficeWeb 應用程式伺服器  <br/> ||443  <br/> ||由商務用 Skype Server 用來連線至 Office Web Apps Server。  <br/> |

**必要的用戶端埠**


|**Port**|**Protocol** (通訊協定)|**附註**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)   <br/> |用於外部使用者存取 web 會議會話。  <br/> |
|443  <br/> |TCP (STUN/MSTURN)   <br/> |用於外部使用者存取 A/V 會話和媒體 (TCP)   <br/> |
|3478  <br/> |UDP (STUN/MSTURN)   <br/> |用於外部使用者存取 A/V 會話和媒體 (UDP)   <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |音訊埠範圍 (至少需要20個埠)   <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |影片埠範圍 (至少需要20個埠) 。  <br/> |
|1024-65535 \*  <br/> |TCP  <br/> |應用程式共用。  <br/> |