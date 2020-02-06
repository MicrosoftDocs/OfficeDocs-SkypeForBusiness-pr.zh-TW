---
title: 整合內部部署整合訊息與商務用 Skype 的部署程式概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: 摘要：在規劃將商務用 Skype 伺服器與 Exchange 2013 或2016整合時，請複習本主題。
ms.openlocfilehash: db6cdbf5297c2397acadcb65ad615533ae6dbe2f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815891"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>整合內部部署整合訊息與商務用 Skype 的部署程式概述
 
**摘要：** 在規劃將商務用 Skype Server 與 Exchange 2013 或2016整合時，請複習本主題。
  
 如果您想要將 Exchange 整合訊息（UM）與商務用 Skype Server 整合，您必須執行本主題中所述的工作。 此外，請務必參閱在[商務用 Skype 中規劃 Exchange 整合訊息整合](unified-messaging.md)中所述的規劃與部署最佳做法。 本主題假設您已將商務用 Skype Server 與 collocated 中繼伺服器一起部署，且您已為使用者啟用商務用 Skype Server，但您可能還沒有執行所有部署和設定步驟來啟用企業語音，如在部署檔中的[商務用 Skype Server 中部署企業語音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。
 
> [!NOTE]
> 在商務用 Skype Server 2019 中，Exchange 整合的郵件功能已不再提供，因為它會使用電話系統來錄製語音信箱訊息，然後將錄製保留在使用者的 Exchange 信箱中。 如需詳細資訊，請參閱[規劃雲端語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。
 
## <a name="unified-messaging-integration-process"></a>整合通訊流程整合程式

> [!IMPORTANT]
> 請務必與貴組織的 Exchange 管理員共同作業，以確認您要執行的工作，以協助確保順利、成功的整合。 
  
|**分**|**步驟**|**必要的群組和角色**|**部署檔**|
|:-----|:-----|:-----|:-----|
|部署下列其中一項：  <br/> •信箱  <br/> Microsoft Exchange Server 2010 或最新 service pack  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |如果您使用的是 Microsoft Exchange Server 2013，請在與商務用 Skype 伺服器相同的林中或不同的林中，安裝下列 Exchange Server 角色：  <br/> •用戶端存取  <br/> •信箱  <br/> 如果 Microsoft Exchange Server 2013 與 Exchange 整合通訊（UM）安裝在不同的林中，請將每個 Exchange 林設定為信任商務用 Skype Server 林。  <br/> 如果您使用的是 Exchange 2010，請在與商務用 Skype 伺服器相同的林中或不同的林中，安裝下列 Exchange 伺服器角色：  <br/> •整合訊息  <br/> •中樞傳輸  <br/> •用戶端存取  <br/> •信箱  <br/> 如果商務用 Skype Server 和 Exchange 整合通訊（UM）是安裝在不同的林中，請將每個 Exchange 林設定為信任商務用 Skype Server 林。  <br/> |企業系統管理員（如果這是組織中的第一個 Exchange 伺服器）  <br/> 或  <br/> Exchange 組織管理員（如果這不是組織中的第一個 Exchange 伺服器）  <br/> |請參閱適用于您 Exchange 伺服器版本的相關檔：  <br/> Exchange Server 2010 或最新的 service pack 部署檔 <br/> Exchange Server 2013 規劃與部署 <br/> Exchange Server 2016 規劃與部署|
|安裝憑證。  <br/> |從信任的根憑證授權單位（CA）下載並安裝每個 Exchange UM 伺服器的憑證。 在執行 Exchange UM 和商務用 Skype Server 的伺服器之間，雙方傳輸層級安全性（MTLS）都需要有證書。  <br/> |人員  <br/> |[在運行 Exchange Server 整合通訊的伺服器上設定憑證](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|建立及設定新的 Exchange UM SIP 撥號計畫。  <br/> |在 Exchange UM 伺服器上，根據貴組織的特定部署需求來建立 SIP 撥號方案。  <br/> |Exchange 組織管理員  <br/> | [在 Microsoft Exchange Server 上設定整合通訊](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|設定 Exchange UM SIP 撥號方案的安全性設定。  <br/> |若要加密企業語音流量，請將 Exchange UM SIP 撥號方案的安全性設定設定為 [ **SIP 安全**] 或 [**安全**的]。 如果您已在您的環境中部署或規劃部署 Lync Phone Edition 裝置，這是一個特別重要的步驟。 若要讓 Lync Phone Edition 裝置在使用 Exchange UM 整合的環境中運作，商務用 Skype Server 加密設定必須與 Exchange UM 撥號方案安全性設定一致。 如需詳細資訊，請參閱部署檔。  <br/> |Exchange 組織管理員  <br/> |若是 Exchange 2010 或最新的 service pack，請參閱：  <br/> [在 UM 撥號方案上設定 VoIP 安全性](https://go.microsoft.com/fwlink/p/?LinkId=268697)。  <br/> 若為 Exchange 2013，請參閱[整合通訊](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|將整合郵件伺服器新增至 Exchange UM SIP 撥號計畫。  <br/> |若要讓新安裝的整合通訊伺服器應答並處理來電，您必須將統一訊息伺服器新增到 UM 撥號方案。 在這種情況下，請將伺服器新增到 Exchange UM SIP 撥號方案。  <br/> |人員  <br/> Exchange Server 系統管理員  <br/> |若為 Exchange 2010 或最新的 service pack，請參閱[查看或設定 UM 伺服器的屬性](https://go.microsoft.com/fwlink/p/?linkId=268682)。  <br/> 若為 Exchange 2013，請參閱[整合通訊](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|使用 SIP 位址設定信箱。  <br/> |將 SIP 位址指派給將使用 Exchange UM 功能之企業語音使用者的信箱。  <br/> |商務用 Skype Server 系統管理員  <br/> Exchange 收件者管理員  <br/> |若為 Exchange 2010 或最新的 service pack，請參閱[修改適用于 UM 的使用者的 SIP 位址](https://go.microsoft.com/fwlink/p/?LinkId=268699)。  <br/> 若為 Exchange 2013，請參閱[整合通訊](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|執行 exchucutil. ps1 腳本。  <br/> |在執行 Exchange UM 服務的伺服器上，開啟 Exchange 管理命令介面，並執行 exchucutil. ps1 腳本，此腳本會執行下列動作： <br/> <br/> •授與商務用 Skype Server 的許可權，以讀取 Exchange UM Active Directory 網域服務物件，特別是在前一個工作中建立的 SIP 撥號方案。  <br/><br/> •在 Active Directory 中為已啟用企業語音之使用者的每個商務用 Skype Server Enterprise Edition 或 Standard Edition 伺服器建立整合通訊 IP 閘道物件。  <br/><br/> •針對每個閘道建立 Exchange UM 查尋群組。 [查尋] 群組試點識別碼將是與對應的閘道相關聯的撥號方案名稱。 如果有一個以上的撥號方案，則需要將這些專案對應至1:1。  <br/> |Exchange 組織管理員  <br/> Exchange 收件者管理員  <br/> |[使用 ExchUCUtil 在 Microsoft Exchange 上設定整合通訊](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|設定商務用 Skype Server 撥號方案。  <br/> |如果您要與 Exchange 2010 整合，請建立新的企業語音撥號方案，其名稱必須符合 Exchange UM 撥號方案的完整功能變數名稱（FQDN）。  <br/> **注意：** 您將需要針對每個 UM 撥號方案進行這項作業。 <br/> 如果您要與 Exchange 2010 SP1 整合，請確定已設定適當的全域/網站層級或池層級的企業語音撥號方案。  <br/> **注意：** 如果您要與 Exchange 2010 SP1 整合，商務用 Skype Server 撥號方案與 Exchange UM SIP 撥號方案名稱不需相符。 <br/> |RTCUniversalServerAdmins  <br/> |[在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|執行 Exchange UM 整合工具。  <br/> | 在商務用 Skype Server 上，執行**ocsumutil**：  <br/>  建立訂閱者存取權及自動語音應答連絡人物件。 <br/>  驗證是否有符合 Exchange UM 撥號方案 FQDN 之名稱的企業語音撥號方案。 如果您執行的是 Exchange 2010 SP1 或更新版本，撥號方案名稱不需要符合，而且您可以略過工具對此所做的警告。 <br/>  此工具的運作方式是掃描 Exchange UM 設定的 Active Directory，並允許商務用 Skype Server 系統管理員來查看、建立及編輯連絡人物件。 <br/> |RTCUniversalServerAdmins*和*RTCUniversalUserAdmins <br/> **重要：** 若要成功執行 ocsumutil，使用者必須屬於這兩個群組。 <br/> **注意：** 若要建立連絡人物件，執行 ocsumutil 的使用者必須擁有儲存新連絡人物件之 Active Directory 組織單位（OU）的正確許可權。 您可以執行**授與 CsOUPermission** Cmdlet 來授與此許可權。 如需詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。 <br/> |[針對商務用 Skype Server 2015 語音信箱設定 Exchange Server 2013 整合通訊](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|如有需要，請執行其他企業語音設定步驟。  <br/> |如果您尚未在伺服器或使用者上設定 [企業語音設定]，請執行下列其中一項或多項操作：  <br/> •部署和設定  <br/> 公用交換式電話網絡（PSTN）閘道和轉送伺服器  <br/> •定義語音原則、PSTN 使用方式記錄，以及傳出通話路由。  <br/> •允許使用者使用企業語音。  <br/> •您可以選擇使用撥號方案設定特定的使用者。  <br/> 根據您所啟用的企業語音功能，可能需要其他配置步驟。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |請參閱下列各節中的主題：  <br/> •[在商務用 Skype 中設定語音原則、PSTN 使用方式記錄及語音路由](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) <br/> •[在商務用 Skype Server 中部署企業語音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|針對 Exchange UM 啟用企業語音使用者。  <br/> |在 Exchange UM 伺服器上，確定已建立統一訊息信箱原則，且每位使用者都有唯一的分機號碼指派，然後讓使用者使用統一訊息。  <br/> |Exchange 收件者管理員  <br/> |若是 Exchange 2010 或最新的 service pack，請參閱為[使用者啟用整合訊息](https://go.microsoft.com/fwlink/p/?LinkId=268701)。  <br/> 若為 Exchange 2013，請參閱[整合通訊](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
   




## <a name="see-also"></a>另請參閱

[在商務用 Skype 中規劃 Exchange 整合訊息整合](unified-messaging.md)
