---
title: 在商務用 Skype Server 中建立主幹設定的新集合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
description: 摘要：瞭解如何使用商務用 Skype Server 控制台建立新的主幹設定設定集合。
ms.openlocfilehash: 8e5694ea57d1a6c921a08921e2d581b501577303
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830593"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中建立主幹設定的新集合 

**摘要：** 瞭解如何使用商務用 Skype Server 控制台建立新的主幹設定設定集合。
  
SIP 主幹設定設定定義轉送伺服器和公用交換電話網路 (PSTN) 閘道、IP-Public 分支 eXchange (PBX) 或會話邊界控制器（在服務提供者上 (SBC) ）之間的關聯性和功能。 這些設定將指定下列項目：
  
- 主幹是否啟用媒體旁路。
    
- 在哪個條件下會傳送即時傳輸控制通訊協定 (RTCP) 封包。
    
- 在每個主幹上是否需要 (SRTP) 加密的安全即時傳輸通訊協定。
    
當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 主幹設定的集合。 此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。
  
使用商務用 Skype Server 控制台建立 SIP 主幹設定設定時，您可以使用下列選項。
  
|**UI 設定**|**PowerShell 參數**|**描述**|
|:-----|:-----|:-----|
|名稱  <br/> |身分識別  <br/> |集合的唯一識別碼。此為唯讀屬性，您無法變更主幹組態設定集合的 Identity。  <br/> |
|描述  <br/> |描述  <br/> |為系統管理員提供儲存設定相關資訊 (例如，主幹組態的用途) 的方法。  <br/> |
|支援的最大早期對話  <br/> |MaxEarlyDialogs  <br/> |服務提供者的 PSTN 閘道、IP-PBX 或 SBC 對其傳送到中繼伺服器的 Invite，可接收的分支回應數上限。  <br/> |
|加密支援等級  <br/> |SRTPMode  <br/> | 指出支援等級，以保護中繼伺服器和服務提供者之 PSTN 閘道、IP-PBX 或 SBC 之間的媒體流量。 若是媒體旁路的情況，此值必須與媒體組態中的 EncryptionLevel 設定相容。 媒體設定是使用 [新的-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmediaconfiguration?view=skype-ps) 及 [CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) Cmdlet 來設定。 <br/>  允許的值為： <br/>  Required：必須使用 SRTP 加密。 <br/>  Optional：如果閘道支援，即會使用 SRTP。 <br/>  Not Supported：不支援 SRTP 加密，因此不會使用此加密。 <br/>  只有閘道設定為使用傳輸層安全性 (TLS) 時，才能使用 SRTPMode。如果將閘道設定為在傳輸時使用傳輸控制通訊協定 (TCP)，系統會從內部將 SRTPMode 設為 Not Supported。<br/> |
|轉接支援  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |如果設定為 **[啟用傳送轉接至閘道]**，表示主幹支援接收來自中繼伺服器的 Refer 要求。  <br/> 如果設定為 **[使用協力廠商撥號控制來啟用轉接]**，表示可以使用 3pcc 通訊協定允許轉接通話略過主控網站。3pcc 也稱為「第三方控制」，當使用第三方來連接一組來電者時 (例如，由接線員撥打從 A 到 B 的電話)，就會發生此情況。<br/> |
|啟用媒體旁路  <br/> |EnableBypass  <br/> |表示此主幹是否啟用媒體旁路。只有在也啟用 **[集中式媒體處理]** 時，才能啟用媒體旁路。<br/> |
|集中式媒體處理  <br/> |ConcentratedTopology  <br/> |指出是否有已知的媒體終端點 (已知的媒體終端點範例是 PSTN 閘道，其媒體終端的 IP 與訊號終端相同)。  <br/> |
|啟用 RTP 栓  <br/> |EnableRTPLatching  <br/> |指出 SIP 主幹是否支援 RTP 栓。RTP 栓是一種技術，可讓 RTP/RTCP 透過 NAT (網路位址轉譯器) 裝置或防火牆連線。  <br/> |
|啟用轉接來電記錄  <br/> |ForwardCallHistory  <br/> |指出是否將透過主幹來轉接來電記錄資訊。  <br/> |
|啟用轉寄 P-Asserted-Identity 資料  <br/> |ForwardPAI  <br/> |指出 P-Asserted-Identity (PAI) 標頭是否會和通話一起轉寄。PAI 標頭提供確認來電者身分識別的方法。  <br/> |
|啟用輸出路由容錯移轉計時器  <br/> |EnableFastFailoverTimer  <br/> |指出閘道未在 10 秒內接聽的撥出電話將會被路由傳送到下一個可用的主幹；如果沒有其他主幹，就會自動捨棄此電話。在網路和閘道回應速度緩慢的組織中，這可能會造成電話平白遭到捨棄。  <br/> |
|關聯的 PSTN 使用方式  <br/> |PSTNUsages  <br/> |指派給主幹的 PSTN 使用方式集合。  <br/> |
|要測試的轉譯號碼  <br/> |不適用  <br/> |可用於進行主幹組態設定臨機測試的電話號碼。  <br/> |
|關聯的轉譯規則  <br/> |OutboundTranslationRulesList  <br/> |套用到由「輸出路由」處理的電話 (路由傳送到 PBX 或 PSTN 目的地的電話) 的電話號碼轉譯規則集合。  <br/> |
|撥打號碼轉譯規則  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |指派給主幹的撥出電話號碼轉譯規則集合。  <br/> |
|測試的電話號碼  <br/> |不適用  <br/> |可用於進行轉譯規則臨機測試的電話號碼。  <br/> |
|撥打號碼  <br/> |不適用  <br/> |指出要測試的電話號碼是來電者的電話號碼。  <br/> |
|撥打的號碼  <br/> |不適用  <br/> |指出要測試的電話號碼是受話者的電話號碼。  <br/> |
   
> [!NOTE]
> 商務用 Skype Server Get-cstrunkconfiguration Cmdlet 支援其他屬性，但不會顯示在商務用 Skype Server 控制台中。 如需詳細資訊，請參閱 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/new-cstrunkconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。
  
### <a name="to-create-new-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台建立新的主幹設定設定

1. 在商務用 Skype Server 控制台中，依序按一下 [ **語音路由**] 和 [ **主幹** 設定]。
    
2. 在 **[主幹組態]** 索引標籤上，按一下 **[新增]**，然後按一下 **[站台主幹]** 以建立在網站範圍的新設定，或按一下 **[集區主幹]** 以建立在服務範圍的新設定。
    
3. 在 **[選取站台]** 或 **[選取服務]** 對話方塊中 (顯示的對話方塊會視您是建立網站範圍或服務範圍的設定而定)，選取新組態設定的位置，然後按一下 **[確定]**。如果對話方塊是空白的，表示沒有空間可建立新設定；例如，如果 **[選取站台]** 對話方塊是空白的，表示您所有的網站都已被指派主幹組態設定集合，且每個網站 (及每項服務) 都只能主控一個此類集合。在這種情況下，您可以刪除現有的集合後再建立新集合，或只是修改現有的集合。
    
4. 在 **[新主幹組態]** 對話方塊中，選取適當的選項，然後按一下 **[確定]**。
    
5. 集合的 **[State]** 屬性將會更新為 **[未認可]**。如果要認可變更，並刪除集合，請依序按一下 **[認可]** 和 **[全部認可]**。
    
6. 在 **[未認可的語音組態設定]** 對話方塊中，按一下 **[確定]**。
    
7. 在 [ **商務用 Skype 伺服器控制台** ] 對話方塊中，按一下 **[確定**]。
    

