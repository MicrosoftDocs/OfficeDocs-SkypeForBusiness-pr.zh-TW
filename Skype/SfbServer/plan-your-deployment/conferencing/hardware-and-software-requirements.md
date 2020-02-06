---
title: 商務用 Skype Server 中的會議硬體和軟體需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 摘要：請閱讀本主題，以瞭解商務用 Skype Server 中的會議硬體和軟體需求。
ms.openlocfilehash: 0d09e0e85e7059e0a761b2822f963765751623e0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815981"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>商務用 Skype Server 中的會議硬體和軟體需求

**摘要：** 若要瞭解商務用 Skype Server 中的會議硬體和軟體需求，請閱讀本主題。

本節說明 web 會議、音訊和影片（A/V）會議、電話撥入式會議以及立即訊息（IM）會議的硬體和軟體需求。 所有會議功能都在前端伺服器上執行;不同類型的會議還有其他需求，如下圖所示。

例如，如果您想要允許電話撥入式會議，您必須部署一個轉送伺服器和一個閘道來連線至公用的交換電話網絡（PSTN）。 如果您想要允許網路會議，您必須確保商務用 Skype Server 可以連線到 Office Web Apps 伺服器。 如果您想要允許外部使用者參與會議，您必須部署邊緣伺服器。

**會議功能與需求**

![會議元件](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 如需有關拓撲考慮的詳細資訊，請參閱[規劃商務用 Skype Server 的會議拓撲](conferencing-topology.md)。

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>前端伺服器的硬體和軟體需求

因為 web 會議、A/V 會議、電話撥入式會議以及 IM 會議都是與前端伺服器 collocated，所以伺服器硬體和軟體需求與前端伺服器相同。 如需這些需求的詳細資訊，請參閱商務用 skype server [2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)與商務用 skype server 2019 的商務用 skype server 2015 或[伺服器需求](../../../SfBServer2019/plan/system-requirements.md)的[環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。

## <a name="requirements-for-web-conferencing"></a>Web 會議的需求

如果您已選擇啟用 [web 會議]，您必須規劃下列各項：

- 存取儲存網路會議內容所用的檔案存放區。

- 與 Office Web Apps Server 整合，這是為了在會議期間共用 PowerPoint 檔案所需要的。

### <a name="file-store"></a>檔案存放區

商務用 Skype Server web 會議服務會儲存在檔存放區中的會議期間共用的內容。 在部署過程中，您必須指定要用來做為標準版 server 或 Enterprise Edition 前端池之檔案存放區的檔案共用。 您可以在檔案存放區中使用現有的檔案共用，或者您可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱（FQDN），以及新檔案共用的資料夾名稱。 如需詳細資訊，請參閱[在商務用 Skype Server 中建立檔案共用](../../deploy/install/create-a-file-share.md)。 網路會議服務會先加密內容，然後再將內容儲存在檔案存放區中。

商務用 Skype 伺服器支援在直接連接的儲存空間（DAS）或儲存區域網路（SAN）上使用檔案共用，包括分散式檔案系統（DFS），以及適用于檔案存放區的獨立磁碟容錯陣列（RAID）。 在商務用 Skype Server 部署嚮導已定義檔案共用的位置之後，商務用 Skype Server 在檔案共用中建立的資料夾結構會類似以下所示：

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

然後，web 會議服務會在 [WebServices] 資料夾中的 [CollabContent] 和 [CollabMetadata] 資料夾中儲存 PowerPoint 投影片、白板、投票及附件等內容。

### <a name="office-web-apps-server"></a>Office Web Apps 伺服器

若要使用網路會議功能，您必須安裝 Office Web Apps Server 並設定商務用 Skype 伺服器與 Office Web Apps 伺服器進行通訊。

Office Web Apps Server 應該安裝在未執行商務用 Skype Server、SQL Server 或任何其他伺服器應用程式的獨立電腦上。 （您不得在該電腦上安裝任何版本的 Office）。任何用來執行 Office Web Apps Server 的電腦也必須安裝一組特定的軟體（包括 .NET Framework 4.5 和 Windows PowerShell 3.0）。 [Microsoft Office Web Apps 部署網站](https://go.microsoft.com/fwlink/p/?linkid=257525)中詳細討論了這些需求，以及有關設定證書和網際網路資訊服務（IIS）的相關資訊。

如需如何設定商務用 Skype Server 與 Office Web Apps Server 搭配使用的相關資訊，請參閱[在商務用 Skype server 中設定與 Office Web Apps server 整合](../../deploy/deploy-conferencing/office-web-app-server.md)。

## <a name="requirements-for-audio-and-video-conferencing"></a>音訊與視訊會議的需求

若要規劃 A/V 會議，您必須瞭解貴組織所需的會議媒體類型所需的網路頻寬。 這可能包含音訊、影片和全景影片。 如果沒有足夠的網路頻寬，使用者體驗可能會嚴重下降。

如需有關會議的音訊和視頻容量規劃的詳細資訊，請參閱[規劃商務用 Skype 的網路需求](../../plan-your-deployment/network-requirements/network-requirements.md)。

您可以使用 [呼叫許可控制] （CAC）來管理由 A/V 會議使用的網路頻寬。 這對受限制的網路非常重要，例如中央與分支網站之間的頻寬連結有限。 如需詳細資訊，請參閱[在商務用 Skype 伺服器中規劃通話許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。

如果您在網路上部署音訊會議，您的使用者將需要音訊裝置（例如耳機）參與音訊會議。 如果您要部署視訊會議，您必須部署影片裝置，例如使用者的網路攝影機。 對於音訊與視頻裝置，裝置部署與使用者訓練是您要考慮的重要步驟。 如需詳細資訊，請參閱[規劃用戶端和裝置](../../plan-your-deployment/clients-and-devices/clients-and-devices.md)。 Microsoft 建議您使用 Microsoft 針對所有裝置類型認證的整合通訊（UC）裝置，以確保最佳的使用者體驗。 如需 UC 認證裝置的詳細資料，請參閱[商務用 Skype 的電話和裝置](https://go.microsoft.com/fwlink/?LinkId=619916)。

## <a name="requirements-for-dial-in-conferencing"></a>電話撥入式會議的需求

電話撥入式會議是商務用 Skype Server 會議工作負載的選用功能，包括各種不同的元件。 某些元件是與電話撥入式會議相關的，而有些則是企業語音元件。 本節說明電話撥入式會議所需元件的需求。 如需有關中繼伺服器與公用交換電話網絡（PSTN）閘道需求的詳細資料，請參閱[商務用 Skype server 中的中繼伺服器元件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)，以及在[商務用 skype Server 的 [拓撲產生器] 中部署轉送伺服器](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)。

### <a name="required-components"></a>必要元件

您必須先安裝下列商務用 Skype 伺服器元件，才能設定電話撥入式會議：

- 整合通訊應用程式服務（UCAS）（稱為應用程式服務）

- 會議助理應用程式

- 會議公告應用程式

- 電話撥入式會議設定網頁

- 至少一個中繼伺服器與至少一個 PSTN 閘道

如果是電話撥入式會議、應用程式服務、會議助理應用程式及會議公告應用程式，與前端伺服器的作業系統需求相同。 如需詳細資訊，請參閱[商務用 Skype server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。

會議助理應用程式與會議公告應用程式要求 Windows Media 格式執行時間已安裝在前端伺服器上。 Windows Media 格式執行時間需要播放 Windows Media 音訊（WMA）檔案，這些檔案是用來等候音樂、錄製的名稱和提示。 如果您是在 Windows Server 2012 或 Windows Server 2012 R2 （我們建議的）上進行安裝，您必須安裝 Microsoft 媒體基礎才能取得 Windows Media 格式執行時間。 如果您是在 Windows 2012 之前的任何版本的 Windows Server 上進行安裝，您必須先確定已安裝 Windows 桌面體驗，才能取得 Windows Media 格式執行時間。

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>電話撥入式會議的音訊檔需求

商務用 Skype Server 不支援自訂語音提示和電話撥入式會議的音樂。 不過，如果您需要變更預設音訊檔案，請參閱 Microsoft 知識庫文章961177，[說明如何在電話撥入式音訊會議中自訂語音提示或音樂](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)檔案。

您也可以使用[Microsoft Lync Server 會議助理自訂語音提示](https://go.microsoft.com/fwlink/p/?LinkId=396880)管理公用程式，在電話來電者加入商務用 Skype 會議時，系統會使用自訂提示來取代預設的語音提示，以提供不同的會議進入體驗。 您可以在企業版或標準版伺服器上安裝自訂語音提示。

會議助理應用程式與會議公告應用程式對於保留的音樂、錄製的名稱及音訊提示檔案有下列需求：

- Windows Media 音訊（WMA）檔案格式

- 16位 mono

- 48 kbps 2-pass CBR （恒定傳輸率）

- 24DB 的語音層級

### <a name="user-requirements-for-dial-in-conferencing"></a>電話撥入式會議的使用者需求

電話撥入式會議使用者必須有指派給其帳戶的唯一電話號碼或副檔名。 此需求支援在電話撥入式會議期間進行驗證。 企業使用者（也就是在貴組織內擁有 Active Directory 網域服務認證及商務用 Skype 伺服器帳戶的使用者）輸入其電話號碼（或分機），以及使用個人識別碼（PIN）撥入會議已驗證的使用者。

## <a name="port-requirements-for-conferencing"></a>會議的埠需求

若要使用會議功能，商務用 Skype Server 必須開啟特定的埠。 下表列出會議的埠需求。 如需所有埠需求的詳細資料，請參閱[伺服器的埠與通訊協定需求](../../plan-your-deployment/network-requirements/ports-and-protocols.md)。

**所需的伺服器埠**


|**伺服器角色**|**服務名稱**|**通道**|**通訊協定**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|
|前端伺服器  <br/> |商務用 Skype Server IM 會議服務  <br/> |5062  <br/> |TCP-OUT  <br/> |用於立即訊息（IM）會議的傳入 SIP 要求。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server Web 會議服務  <br/> |8057  <br/> |TCP （TLS）  <br/> |用來偵聽來自用戶端的永久性共用物件模型（PSOM）連線。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server Web 會議相容性服務  <br/> |8058  <br/> |TCP （TLS）  <br/> |用來從 Live Meeting 用戶端和舊版的商務用 Skype Server 中監聽永久性共用物件模型（PSOM）連線。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server 音訊/視訊會議服務  <br/> |5063  <br/> |TCP-OUT  <br/> |用於音訊/視頻（A/V）會議的傳入 SIP 要求。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server 音訊/視訊會議服務  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |用於視訊會議的媒體埠範圍。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server 會議助理服務（電話撥入式會議）  <br/> |5064  <br/> |TCP-OUT  <br/> |用於電話撥入式會議的傳入 SIP 要求。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server 會議助理服務（電話撥入式會議）  <br/> |5072  <br/> |TCP-OUT  <br/> |用於接聽的傳入 SIP 要求（撥入會議）。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server 應用程式共用服務  <br/> |5065  <br/> |TCP-OUT  <br/> |用於應用程式共用的傳入 SIP 偵聽要求。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server 應用程式共用服務  <br/> |49152-65535  <br/> |TCP-OUT  <br/> |用來共用應用程式的媒體埠範圍。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server 會議宣告服務  <br/> |5073  <br/> |TCP-OUT  <br/> |用於商務用 Skype Server 會議宣告服務的傳入 SIP 要求（也就是電話撥入式會議）。  <br/> |
|所有內部伺服器  <br/> |各種各樣  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |在所有內部伺服器上，音訊會議所用的媒體埠範圍。 是由所有終止音訊的伺服器所使用：前端伺服器（適用于商務用 Skype Server 會議助理服務、商務用 Skype Server 會議宣告服務，以及商務用 Skype Server 音訊/視訊會議服務）和中繼伺服器。  <br/> |
|Office Web Apps 伺服器  <br/> ||443  <br/> ||由商務用 Skype Server 用來連線到 Office Web Apps 伺服器。  <br/> |

**所需的用戶端埠**


|**通道**|**通訊協定**|**筆記**|
|:-----|:-----|:-----|
|443  <br/> |TCP （PSOM/TLS）  <br/> |用於外部使用者存取網路會議會話。  <br/> |
|443  <br/> |TCP （STUN/MSTURN）  <br/> |供外部使用者存取 A/V 會話及媒體（TCP）  <br/> |
|3478  <br/> |UDP （STUN/MSTURN）  <br/> |供外部使用者存取 A/V 會話及媒體（UDP）  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |音訊埠範圍（所需的最小20個埠）  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |影片埠範圍（需要20個埠的最小值）。  <br/> |
|1024-65535\*  <br/> |TCP-OUT  <br/> |應用程式共用。  <br/> |


