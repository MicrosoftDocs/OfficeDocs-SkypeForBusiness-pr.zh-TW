---
title: 商務用 Skype Server 中的架構類別和描述
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: 本節說明商務用 Skype Server 所使用的所有架構類別。
ms.openlocfilehash: d7f05cd76074740e49f3972c97875e8993dd7b06
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743259"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>商務用 Skype Server 中的架構類別和描述
 
本節說明商務用 Skype Server 所使用的所有架構類別。 
  
## <a name="schema-classes-and-descriptions"></a>架構類別和描述

|**類別**|**描述**|**註解**|
|:-----|:-----|:-----|
|Mail-Recipient  <br/> |Exchange整合通訊 (UM) 電子郵件收件者。  <br/> |此輔助類別與 Exchange UM 共用。  <br/> |
|msRTCSIP ApplicationContacts  <br/> |此類別是多個應用程式連絡人的容器，本身不包含任何屬性。  <br/> |Microsoft Office 通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-ApplicationServer  <br/> |此類別包含一個項目，代表整合通訊應用程式服務 (UCAS) 的服務控制點。  <br/> |Office 通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ApplicationServerService  <br/> |此類別提供從特定集區到其應用程式服務的關聯。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ApplicationServerSettings  <br/> |此輔助類別用於 msRTCSIP-ApplicationServer 包含代表應用程式服務實例設定的屬性。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-Archive (過時的)  <br/> |msRTCSIP-GlobalContainer 的這個輔助類別包含與封存相關的所有設定。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-ArchivingServer (過時的)  <br/> |此類別代表單一立即訊息封存伺服器。將電腦當做立即訊息封存伺服器 (例如，已安裝「立即訊息封存服務」的電腦) 啟動時，就會建立此類別的執行個體。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories  <br/> |此類別是多個會議目錄執行個體的容器，本身不包含任何屬性。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ConferenceDirectory  <br/> |這個類別包含代表特定會議目錄設定的屬性。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |一般服務控制點 (SCP) 將電腦指定為執行商務用 Skype Server 的伺服器。  <br/> |Lync 2010 中的新功能。  <br/> |
|msRTCSIP DefaultCWABank  <br/> |此輔助類別包含商務用 Skype Web 應用程式銀行的設定。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-Domain  <br/> |此類別包含的屬性可定義 SIP 登錄器所設定的網域。  <br/> |-  <br/> |
|msRTCSIP EdgeProxy  <br/> |此類別容器代表單一 Access Edge service。 由於 Access Edge service 是部署在周邊網路中，而且客戶通常不允許來自周邊網路的 Active Directory 網域服務存取，所以 Access Edge service 的實例不會加入內部網路的 Active Directory 網路。 因此 AD DS 中不會自動註冊存取 Proxy。 管理員必須手動設定 AD DS 中每個 Access Edge service 實例的存在。  <br/> |-  <br/> |
|msRTCSIP EnterpriseMCUSettings  <br/> |msRTCSIP-MCU 的這個輔助類別包含代表會議伺服器設定的屬性。  <br/> |Microsoft Office 通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP EnterpriseMediationServerSettings  <br/> |msRTCSIP-MediationServer 的這個輔助類別包含代表中繼伺服器設定的屬性。  <br/> |Office 通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP EnterpriseServerSettings  <br/> |msRTCSIP-Server 的這個輔助類別包含代表 SIP 伺服器設定的屬性。  <br/> |-  <br/> |
|msRTCSIP-同盟  <br/> |msRTCSIP-GlobalContainer 的這個輔助類別包含與同盟相關的所有設定。  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |此類別包含所有在商務用 Skype Server 部署中套用的設定。  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (過時的)  <br/> |此類別代表單一 Office 通訊伺服器會議原則。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP GlobalTopologySetting  <br/> |本機全域拓撲設定物件。  <br/> |Lync Server 2010 的新增功能。  <br/> |
|msRTCSIP GlobalTopologySettings  <br/> |用以存放全域拓撲設定物件的容器。  <br/> |Lync Server 2010 的新增功能。  <br/> |
|msRTCSIP LocalNormalization  <br/> |此類別是代表一個位置正規化規則執行個體的容器。  <br/> |-  <br/> |
|msRTCSIP LocationContactMapping  <br/> |此類別是由會議語音應答應用程式所建立，並保留用來依地區分類會議電話號碼的屬性。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP LocationContactMappings  <br/> |此類別是多個位置連絡人對應執行個體的容器，本身不包含任何屬性。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP Microsoft.rtc.management.writableconfig.policy.voice.locationprofile  <br/> |此類別是代表特定位置設定檔的容器。  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (過時的)  <br/> |此類別是多個位置設定檔的容器，本身不包含任何屬性。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-LocalNormalizations (過時的)  <br/> |此類別是多個本機正規化規則的容器，本身不包含任何屬性。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-MCU  <br/> |此類別代表單一會議伺服器。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP MCUFactories  <br/> |此類別包含多個 msRTCSIP-MCUFactory 類別，本身不包含任何屬性。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP-MCUFactory  <br/> |此類別是代表單一媒體類型之會議伺服器中心的容器。每當啟動這個特定類型和廠商的第一個會議伺服器時，就會建立此類別的執行個體。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP MCUFactoryService  <br/> |此類別提供從特定集區到其會議伺服器中心的關聯。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP-MediationServer  <br/> |此類別包含「中繼伺服器」的服務控制點項目。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP-Meeting (過時的)  <br/> |msRTCSIP-GlobalContainer 的這個輔助類別包含代表可設定會議設定的屬性。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP 行動性  <br/> |用以儲存全域行動性設定的容器。  <br/> |-  <br/> |
|msRTCSIP MonitoringServer  <br/> |此類別包含代表單一監控伺服器設定的屬性。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-PhoneRoute (過時的)  <br/> |此類別是代表一個或一組閘道之最低成本路由執行個體的容器。這項資訊供所有 Enterprise Pool 或執行 Standard Edition 的伺服器，用於將傳出通話以最符合成本效益的方式路由到公用交換電話網路 (PSTN)。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-PhoneRoutes (過時的)  <br/> |此類別是多個最低成本路由的容器，本身不包含任何屬性。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-Policies (過時的)  <br/> |此類別包含多個 Lync Server policy 類別，本身沒有任何屬性。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP 集區  <br/> |此類別代表單一商務用 Skype Server 集區。  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |此類別包含多個商務用 Skype Server 集區，本身沒有任何屬性。  <br/> |-  <br/> |
|msRTCSIP PoolService  <br/> |此類別代表集區的服務控制點連線點。位於集區內的使用者擁有自己的 msRTCSIP-PrimaryHomeServer 屬性，指向此類別的執行個體。  <br/> |-  <br/> |
|msRTCSIP-目前狀態  <br/> |用以儲存全域顯示狀態設定的容器。  <br/> |-  <br/> |
|msRTCSIP-註冊機構  <br/> |msRTCSIP-GlobalContainer 的這個輔助類別包含代表 SIP 登錄器伺服器所維護使用者設定的屬性。  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (過時的)  <br/> |此類別是代表電話路由使用方式執行個體的容器。電話路由使用方式類別由一個屬性欄位和一個描述欄位組成。屬性欄位定義使用方式類型，描述欄位則讓系統管理員能夠描述此屬性在電話路由中的使用方式。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-RouteUsages (過時的)  <br/> |此類別包含 msRTCSIP-RouteUsage 類別的多個執行個體，本身沒有任何屬性。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-搜尋  <br/> |msRTCSIP-GlobalContainer 的這個輔助類別，包含限制並控制搜尋結果範圍的屬性。  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |此類別代表執行商務用 Skype Server 的單一伺服器。  <br/> |-  <br/> |
|msRTCSIP 服務  <br/> |此類別包含全域設定容器和 msRTCSIP-Domain 物件。  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |這個類別包含代表受信任會議伺服器相關設定的屬性。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP TrustedMCUs  <br/> |此類別包含 msRTCSIP-TrustedMCU 類別的多個執行個體，本身沒有任何屬性。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP TrustedProxies  <br/> |此類別包含多個 msRTCSIP-TrustedProxy 類別，本身不包含任何屬性。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP-TrustedProxy  <br/> |此類別是代表執行 Proxy 伺服器之伺服器的容器。每當在加入 AD DS 的電腦上啟動新的 Proxy 伺服器時，就會建立此類別的執行個體。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP TrustedServer  <br/> |此類別包含代表受信任伺服器相關設定的屬性。  <br/> |-  <br/> |
|msRTCSIP TrustedService  <br/> |此類別是代表受信任服務的容器，這類服務可使用「可全域路由傳送使用者代理程式 URI」(GRUU) 位址進行路由。 此類別的實例會在啟用商務用 Skype Server 所信任的新伺服器時建立。 這個受信任的伺服器必須加入 Active Directory 網域。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP TrustedServices  <br/> |此類別是多部 GRUU 伺服器的容器，本身不包含任何屬性。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP TrustedWebComponentsServer  <br/> |此類別包含代表受信任 Web 元件相關設定的屬性。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP TrustedWebComponentsServers  <br/> |此類別包含 msRTCSIP-TrustedWebComponentServer 類別的多個執行個體，本身沒有任何屬性。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP-UnifiedCommunications (過時的)  <br/> |msRTCSIP-GlobalContainer 的這個輔助類別包含與整合通訊相關的屬性。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-WebComponents  <br/> |此類別包含 Internet Information Server (IIS) 的服務控制點。它會將伺服器識別為 Web 元件伺服器。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP WebComponentsService  <br/> |此類別提供從特定集區到該集區所將使用 Web 元件的關聯。  <br/> |通訊伺服器2007的新增功能。  <br/> |
|msRTCSIP WebComponentSettings  <br/> |msRTCSIP-WebComponents 的這個輔助類別包含代表 Web 元件相關設定的屬性。  <br/> |通訊伺服器2007的新增功能。  <br/> |
   

