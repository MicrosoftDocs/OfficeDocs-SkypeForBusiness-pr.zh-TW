---
title: 商務用 Skype Server 中的架構類別和描述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: 本節將說明商務用 Skype Server 所使用的所有架構類別。
ms.openlocfilehash: 6cb67c47c20ecb9cc6af79e51ebc05c332fd0bf3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815471"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>商務用 Skype Server 中的架構類別和描述
 
本節將說明商務用 Skype Server 所使用的所有架構類別。 
  
## <a name="schema-classes-and-descriptions"></a>架構類別和描述

|**靜態類**|**說明**|**批註**|
|:-----|:-----|:-----|
|郵件-收件者  <br/> |Exchange 整合通訊（UM）電子郵件收件者。  <br/> |這個輔助類別是與 Exchange UM 共用。  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |這個類別是多個應用程式連絡人的容器，且不包含任何屬性本身。  <br/> |Microsoft Office 通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-ApplicationServer  <br/> |這個類別會保留針對整合通訊應用程式服務（UCAS）實例之服務控制點的專案。  <br/> |Office 通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |這個類別提供從特定的池中到其應用程式服務的關聯。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |此輔助類別可 msRTCSIP-ApplicationServer 保留代表應用程式服務實例之設定的屬性。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP 封存（已過時）  <br/> |此輔助類別可 msRTCSIP-GlobalContainer 保留與封存相關的所有設定。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-ArchivingServer （已過時）  <br/> |這個類別代表單一立即訊息存檔伺服器。 當電腦啟動為立即訊息存檔伺服器（例如已安裝立即訊息存檔服務的電腦）時，就會建立這個類別的實例。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |這個類別是多個會議目錄實例的容器，且不包含任何屬性本身。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |這個類別會保留代表特定會議目錄設定的屬性。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |一般服務控制點（SCP），可將電腦指定為執行商務用 Skype Server 的伺服器。  <br/> |Lync 2010 的新功能。  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |這個輔助類別會保留商務用 Skype Web App 銀行的設定。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-網域  <br/> |這個類別會保留定義 SIP 註冊機構的已設定網域的屬性。  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |這個類別容器代表單一存取邊緣服務。 因為 Access Edge 服務是在周邊網路中部署，而且客戶通常不允許從周邊網路存取 Active Directory 網域服務，所以 Access Edge 服務的實例不會加入內部網路的 Active Directory 網路。 因此，Access proxy 不會自動在 AD DS 中註冊。 系統管理員必須在 AD DS 中手動設定每個 Access Edge 服務實例的存在。  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |這個輔助類別至 msRTCSIP-MCU 保留代表會議服務器設定的屬性。  <br/> |Microsoft Office 通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |此輔助類別可 msRTCSIP-MediationServer 保留代表對轉送伺服器的設定的屬性。  <br/> |Office 通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |此輔助類別可 msRTCSIP-Server 封存屬性代表 SIP 伺服器的設定。  <br/> |-  <br/> |
|msRTCSIP-同盟  <br/> |此輔助類別至 msRTCSIP-GlobalContainer 會保留與同盟相關的所有設定。  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |這個類別會保留所有適用于商務用 Skype Server 部署的設定。  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy （已過時）  <br/> |這個類別代表單一的 Office 通訊伺服器會議原則。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |本機全域拓撲設定物件。  <br/> |Lync Server 2010 的新功能。  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |容納全域拓撲設定物件的容器。  <br/> |Lync Server 2010 的新功能。  <br/> |
|msRTCSIP-LocalNormalization  <br/> |這個類別是一個代表位置正常化規則實例的容器。  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |這個類別是由會議助理應用程式所建立，並保留用於依地區分類會議電話號碼的屬性。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |這個類別是多個位置連絡人對應的實例容器，且不包含任何屬性本身。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-LocationProfile  <br/> |這個類別是代表特定位置設定檔的容器。  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles （已過時）  <br/> |這個類別是多個位置設定檔的容器，且不包含任何屬性本身。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-LocalNormalizations （已過時）  <br/> |這個類別是多個局部正常化規則的容器，且不包含任何屬性本身。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-MCU  <br/> |這個類別代表單一的會議服務器。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-MCUFactories  <br/> |這個類別會保留多個 msRTCSIP MCUFactory 類別，而且沒有屬性本身。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-MCUFactory  <br/> |這個類別是一個代表單一中型類型會議服務器工廠的容器。 此類別的實例會在啟用此特定類型和供應商的第一個會議服務器時建立。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |這個類別提供從特定的池中到它的會議服務器工廠的關聯。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-MediationServer  <br/> |這個類別會儲存轉送伺服器的服務控制點專案。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-會議（已過時）  <br/> |此輔助類別可 msRTCSIP-GlobalContainer 保留代表可設定會議設定的屬性。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-行動性  <br/> |儲存全域行動設定的容器。  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |這個類別會保留代表單一監視伺服器設定的屬性。  <br/> |通訊伺服器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-PhoneRoute （已過時）  <br/> |這個類別是代表閘道或閘道組之最小成本路線實例的容器。 此資訊是由執行標準版的所有企業池或伺服器所使用，以最經濟划算的方式將撥出電話路由到公用交換電話網絡（PSTN）。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-PhoneRoutes （已過時）  <br/> |這個類別是多個最低成本路由的容器，而且不包含任何屬性本身。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-原則（已過時）  <br/> |這個類別會保留多個 Lync 伺服器原則類別，而且沒有任何屬性本身。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-Pool  <br/> |此類別代表單一商務用 Skype 伺服器池。  <br/> |-  <br/> |
|msRTCSIP-Pool  <br/> |此類別會保留多個商務用 Skype 伺服器池，且不具備任何屬性本身。  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |這個類別代表一個池子的服務控制 pointservice 控點。 主機上託管的使用者會將其 msRTCSIP-PrimaryHomeServer 屬性指向這個類別的實例。  <br/> |-  <br/> |
|msRTCSIP-目前狀態  <br/> |儲存全域目前狀態設定的容器。  <br/> |-  <br/> |
|msRTCSIP-註冊機構  <br/> |此輔助類別可 msRTCSIP-GlobalContainer 保留代表 SIP 註冊機構所維護之使用者設定的屬性。  <br/> |-  <br/> |
|msRTCSIP-RouteUsage （已過時）  <br/> |這個類別是代表手機路線使用量的實例的容器。 電話路線使用類別由屬性欄位和描述欄位組成。 屬性欄位會定義用法類型。 [描述] 欄位可讓系統管理員描述手機路線中這個屬性的使用方式。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-RouteUsages （已過時）  <br/> |這個類別會保留 msRTCSIP-RouteUsage 類別的多個實例，且不具備任何屬性本身。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-搜尋  <br/> |這個輔助類別至 msRTCSIP-GlobalContainer 保留限制及控制搜尋結果範圍的屬性。  <br/> |-  <br/> |
|msRTCSIP-伺服器  <br/> |此類別代表執行商務用 Skype 伺服器的單一伺服器。  <br/> |-  <br/> |
|msRTCSIP-服務  <br/> |這個類別會保留全域設定容器與 msRTCSIP 網域物件。  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |這個類別會保留代表受信任的會議服務器設定的屬性。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |這個類別會保留 msRTCSIP-TrustedMCU 類別的多個實例，且不具備任何屬性本身。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-TrustedProxies  <br/> |這個類別會保留多個 msRTCSIP TrustedProxy 類別，且不包含任何屬性本身。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-TrustedProxy  <br/> |這個類別是一個代表執行 Proxy 伺服器的伺服器容器。 當您在已加入 AD DS 的電腦上啟用新的 Proxy 伺服器時，就會建立這個類別的實例。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-TrustedServer  <br/> |這個類別會保留代表信任伺服器設定的屬性。  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |這個類別是一個代表可透過全域路由使用者代理程式 URI （GRUU）位址路由的信任服務的容器。 當啟用商務用 Skype Server 信任的新伺服器時，就會建立這個類別的實例。 這個受信任的伺服器必須加入 Active Directory 網域。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-TrustedServices  <br/> |這個類別是多個 GRUU 伺服器的容器，且不包含任何屬性本身。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |這個類別會保留代表信任網頁元件設定的屬性。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |這個類別會保留 msRTCSIP-TrustedWebComponentServer 類別的多個實例，且不具備任何屬性本身。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-UnifiedCommunications （已過時）  <br/> |此輔助類別可 msRTCSIP-GlobalContainer 保留與整合通訊相關的屬性。  <br/> |在 Lync Server 2010 中已過時。  <br/> |
|msRTCSIP-WebComponents  <br/> |這個類別會保留網際網路 information Server （IIS）的服務控制 pointservice 控制點。 它會將伺服器識別為網頁元件伺服器。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-WebComponentsService  <br/> |這個類別提供從特定的池中到該池將使用之網頁元件的關聯。  <br/> |通訊伺服器2007中的新功能。  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |此輔助類別可 msRTCSIP-WebComponents 保留代表網頁元件設定的屬性。  <br/> |通訊伺服器2007中的新功能。  <br/> |
   

