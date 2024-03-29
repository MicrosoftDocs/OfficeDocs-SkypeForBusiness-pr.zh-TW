---
title: 整合內部部署整合通訊和商務用 Skype 的部署程式概述
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: 摘要：在規劃將商務用 Skype Server 與 Exchange 2013 或2016整合時，請參閱本主題。
ms.openlocfilehash: 10c503d2ea53035539b8607d7d757d6d070a4f18
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62418386"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>整合內部部署整合通訊和商務用 Skype 的部署程式概述
 
**總結：** 在規劃將商務用 Skype Server 與 Exchange 2013 或2016整合時，請複習本主題。
  
 如果您想要將 Exchange 整合通訊 (UM) 與商務用 Skype Server 整合，您必須執行本主題中所述的工作。 此外，請務必查看在[商務用 Skype 中規劃 Exchange 整合通訊整合](unified-messaging.md)所述的規劃及部署最佳作法。 本主題假設您已使用組合轉送伺服器部署商務用 Skype Server，且已啟用使用者商務用 Skype Server，但是您可能尚未執行所有的部署及設定步驟來啟用企業語音，如[部署企業語音中的「部署所述。](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)部署檔中的商務用 Skype Server。
 
> [!NOTE]
> 商務用 Skype Server 2019 中不再提供 Exchange 的整合通訊，其使用電話系統來錄製語音信箱訊息，然後在使用者的 Exchange 信箱中留下記錄。 如需詳細資訊，請參閱[Plan 雲端語音信箱 service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 。
 
## <a name="unified-messaging-integration-process"></a>Unified Messaging 整合程序

> [!IMPORTANT]
> 請務必與組織的 Exchange 系統管理員合作，以確認每個所要執行的工作，以協助確保順利、成功的整合。 
  
|**階段**|**步驟**|**所需群組和角色**|**部署文件**|
|:-----|:-----|:-----|:-----|
|部署下列其中一項：  <br/> •信箱  <br/> Microsoft Exchange Server 2010 或最新的 service pack  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |如果您使用 Microsoft Exchange Server 2013，請在相同的樹系或不同的樹系中，安裝下列 Exchange Server 角色，以商務用 Skype Server：  <br/> •用戶端存取  <br/> •信箱  <br/> 如果 Microsoft Exchange Server 2013 和 Exchange 整合通訊 (UM) 安裝在不同的樹系中，請將每個 Exchange 樹系設定為信任商務用 Skype Server 樹系。  <br/> 如果您使用 Exchange 2010，請在相同的樹系或不同的樹系中，安裝下列 Exchange Server 角色，以商務用 Skype Server：  <br/> •整合通訊  <br/> • Hub Transport  <br/> •用戶端存取  <br/> •信箱  <br/> 如果商務用 Skype Server 和 Exchange 整合通訊 (UM) 安裝在不同的樹系中，請將每個 Exchange 樹系設定為信任商務用 Skype Server 樹系。  <br/> |企業的系統管理員 (如果這是組織中的第一部 Exchange Server)  <br/> -或-  <br/> Exchange 組織系統管理員 (如果這不是組織中的第一部 Exchange Server)  <br/> |請參閱您的 Exchange Server 版本所適用的文件：  <br/> Exchange Server 2010 或最新的 service pack 部署檔 <br/> Exchange Server 2013 規劃及部署 <br/> Exchange Server 2016 規劃及部署|
|安裝憑證。  <br/> |從受信任的憑證授權單位單位 (CA) 下載和安裝每個 Exchange UM 伺服器的憑證。 在執行 Exchange UM 及商務用 Skype Server 之伺服器間，相互傳輸層級安全性 (MTLS) 所需的憑證。  <br/> |系統管理員  <br/> |[在執行 Exchange Server 整合通訊的伺服器上設定憑證](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|建立並設定新的 Exchange UM SIP 撥號對應表。  <br/> |在 Exchange UM 伺服器上，根據您組織的特定部署需求建立 SIP 撥號對應表。  <br/> |Exchange 組織系統管理員  <br/> | [設定 Microsoft Exchange Server 的整合通訊](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|設定 Exchange UM SIP 撥號對應表的安全性設定。  <br/> |若要加密企業語音流量，請將 Exchange UM SIP 撥號對應表上的安全性設定設定為 [ **SIP 安全**] 或 [**安全**]。 如果您已在環境中部署或規劃部署 Lync 電話 Edition 裝置，則此為特別重要的步驟。 若要在具有 Exchange UM 整合的環境中運作 Lync 電話 Edition 裝置，商務用 Skype Server 加密設定必須與 Exchange UM 撥號對應表安全性設定對齊。 如需詳細資訊，請參閱＜部署＞文件。  <br/> |Exchange 組織系統管理員  <br/> |對於 Exchange 2010 或最新的 Service Pack，另請參閱：  <br/> [在 UM 撥號對應表上設定 VoIP 安全性](/previous-versions/office/exchange-server-2010/bb201721(v=exchg.141))。  <br/> 如 Exchange 2013，請參閱[整合通訊](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|將整合通訊伺服器新增至 Exchange UM SIP 撥號對應表。  <br/> |若要讓新安裝的 Unified Messaging 伺服器能夠接聽及處理來電，您必須將 Unified Messaging 伺服器新增至 UM 撥號對應表。 在此情況下，請將伺服器新增至 Exchange UM SIP 撥號對應表。  <br/> |系統管理員  <br/> Exchange Server 系統管理員  <br/> |如 Exchange 2010 或最新的 service pack，請參閱[View or Configure UM Server 的屬性](/previous-versions/office/exchange-server-2010/aa998815(v=exchg.141))。  <br/> 如 Exchange 2013，請參閱[整合通訊](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|以 SIP 位址設定信箱。  <br/> |將 SIP 位址指派給將使用 Exchange UM 功能之企業語音使用者的信箱。  <br/> |商務用 Skype Server 管理員  <br/> Exchange 收件者系統管理員  <br/> |針對 Exchange 2010 或最新的 service pack，請參閱[Modify a UM-Enabled User 的 SIP 位址](/previous-versions/office/exchange-server-2010/dd335189(v=exchg.141))。  <br/> 如 Exchange 2013，請參閱[整合通訊](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|執行 exchucutil.ps1 指令碼。  <br/> |在執行 Exchange UM 服務的伺服器上，開啟 Exchange 管理命令介面，並執行 exchucutil.ps1 腳本，這會執行下列作業： <br/> <br/> •授與商務用 Skype Server Exchange 讀取 UM Active Directory 網域服務物件（特別是先前任務中建立的 SIP 撥號對應表）的許可權。  <br/><br/> •為主控已啟用企業語音之使用者的每個商務用 Skype Server Enterprise Edition 集區或 Standard Edition 伺服器建立 Active Directory 中的整合通訊 IP 閘道物件。  <br/><br/> •建立每個閘道的 Exchange UM 群組搜尋。 群組搜尋引導識別碼將會是與對應閘道關聯的撥號對應表名稱。 如果有多個撥號對應表，則這些項目必須要一一對應。  <br/> |Exchange 組織系統管理員  <br/> Exchange 收件者系統管理員  <br/> |[使用 ExchUCUtil.ps1設定 Microsoft Exchange 的整合通訊](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|設定商務用 Skype Server 撥號對應表。  <br/> |如果您要與 Exchange 2010 整合，請建立新的企業語音撥號對應表，其名稱符合 Exchange UM 撥號對應表完整功能變數名稱 (FQDN) 。  <br/> **注意：** 您必須為每個 UM 撥號對應表執行這項作業。 <br/> 如果您要與 Exchange 2010 SP1 整合，請確定已設定適當的全域/網站層級或集區層級企業語音撥號對應表。  <br/> **注意：** 如果您要與 Exchange 2010 SP1 整合，商務用 Skype Server 撥號對應表及 Exchange UM SIP 撥號對應表名稱不需要相符。 <br/> |RTCUniversalServerAdmins  <br/> |[在商務用 Skype Server 中建立或修改撥號對應表](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|執行 Exchange UM 整合工具。  <br/> | 在商務用 Skype Server 上，執行 **ocsumutil.exe**，這會：  <br/>  建立「訂戶存取」與「自動語音應答」連絡人物件。 <br/>  驗證是否有企業語音撥號對應表，其名稱符合 Exchange UM 撥號對應表 FQDN。 如果您正在執行 Exchange 2010 SP1 或更新版本，撥號對應表名稱不需要比對，您可以忽略此工具對此的警告。 <br/>  此工具的運作方式是掃描 Exchange UM 設定的 Active Directory，並允許商務用 Skype Server 管理員來查看、建立及編輯連絡人物件。 <br/> |RTCUniversalServerAdmins  *和*  RTCUniversalUserAdmins <br/> **重要：** 若要成功執行 ocsumutil.exe，使用者必須屬於這兩個群組。 <br/> **注意：** 若要建立連絡人物件，執行 ocsumutil.exe 的使用者必須具有儲存新連絡人物件的 Active Directory 組織單位 (OU) 的適當許可權。 您可以執行 **Grant-CsOUPermission** Cmdlet 來授與此許可權。 如需詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。 <br/> |[設定商務用 Skype Server 語音信箱 Exchange Server 整合通訊](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|如有必要，請執行其他企業語音設定步驟。  <br/> |如果您尚未設定伺服器或使用者的企業語音設定，請執行下列一或多項作業：  <br/> •部署及設定  <br/> 公用交換電話網路 (PSTN) 閘道和轉送伺服器  <br/> •定義語音原則、PSTN 使用方式記錄和撥出電話路由。  <br/> •為使用者啟用企業語音。  <br/> •（選用）使用撥號對應表設定特定使用者。  <br/> 視您所啟用的企業語音功能之不同，您可能必須執行其他設定步驟。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |請參閱以下幾節中的主題：  <br/> •[在商務用 Skype 中設定語音原則、PSTN 使用方式記錄和語音路由](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) <br/> •[在商務用 Skype Server 中部署企業語音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|啟用企業語音 Exchange UM 的使用者。  <br/> |在 Exchange UM 伺服器上，確定已建立整合通訊信箱原則，且每位使用者都有唯一的分機號碼指派，然後為使用者啟用整合通訊。  <br/> |Exchange 收件者系統管理員  <br/> |針對 Exchange 2010 或最新的 service pack，請參閱[Enable a User for a 整合通訊](/previous-versions/office/exchange-server-2010/bb124147(v=exchg.141))。  <br/> 如 Exchange 2013，請參閱[整合通訊](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
   




## <a name="see-also"></a>另請參閱

[規劃商務用 Skype 中的 Exchange 整合通訊整合](unified-messaging.md)