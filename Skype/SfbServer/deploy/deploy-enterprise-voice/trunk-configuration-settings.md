---
title: 在商務用 Skype Server 中建立新的主幹設定設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
description: '摘要: 瞭解如何使用商務用 Skype Server [控制台] 來建立新的主幹設定設定集合。'
ms.openlocfilehash: b3772901f1fa7137a358d4519ea9473f237ba85e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193263"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中建立新的主幹設定設定集合 

**摘要:** 瞭解如何使用商務用 Skype Server [控制台] 來建立新的主幹設定設定集合。
  
SIP 幹線設定設定會定義在服務提供者上, exchange 中繼伺服器與公用交換式電話網絡 (PSTN) 閘道、IP 公用分支 eXchange (PBX) 或會話邊界控制器 (SBC) 之間的關聯性與能力。 這些設定會以指定的方式執行以下操作:
  
- 是否應該在 trunks 上啟用媒體旁路。
    
- 傳送即時傳輸控制通訊協定 (RTCP) 資料包的條件。
    
- 每個幹線是否都需要安全的即時傳輸通訊協定 (SRTP) 加密。
    
當您安裝商務用 Skype Server 時, 系統會為您建立一個全域 SIP 中繼設定。 此外, 管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 上建立自訂設定集合。
  
使用商務用 Skype Server [控制台] 建立 SIP 中繼設定設定時, 您可以使用下列選項。
  
|**UI 設定**|**PowerShell 參數**|**說明**|
|:-----|:-----|:-----|
|名稱  <br/> |Identity  <br/> |集合的唯一識別碼。 這個屬性是唯讀的;您無法變更主幹設定集合的身分識別。  <br/> |
|說明  <br/> |說明  <br/> |提供一種方式, 讓系統管理員可以儲存有關設定的附加資訊 (例如, 主幹設定的用途)。  <br/> |
|支援的最大早期對話方塊  <br/> |MaxEarlyDialogs  <br/> |在服務提供者上, PSTN 閘道、IP PBX 或 SBC 的分叉回應數目上限, 可能會收到傳送到轉送伺服器的邀請。  <br/> |
|加密支援層級  <br/> |SRTPMode  <br/> | 指示在服務提供者上的中繼伺服器與 PSTN 閘道、IP PBX 或 SBC 之間保護媒體流量的支援層級。 若是媒體旁路的情況，此值必須與媒體組態中的 EncryptionLevel 設定相容。 媒體設定是使用[新的-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmediaconfiguration?view=skype-ps)和[CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) Cmdlet 來設定。 <br/>  允許的值為： <br/>  必要: 必須使用 SRTP 加密。 <br/>  [選用]: 如果閘道支援, 則會使用 SRTP。 <br/>  不支援: 不支援 SRTP 加密, 因此將無法使用。 <br/>  只有在閘道設定為使用傳輸層安全性 (TLS) 時, 才會使用 SRTPMode。 如果將閘道設定為傳輸控制通訊協定 (TCP) 作為傳輸, 則 SRTPMode 會在內部設定為 [不支援]。 <br/> |
|請參閱支援人員  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |如果設定為**允許傳送參照閘道**, 則表示主幹支援從中繼伺服器接收參考要求。  <br/> 如果設定為**啟用 [使用協力廠商通話控制**], 則表示3pcc 通訊協定可以用來允許轉接呼叫繞過託管的網站。 3pcc 亦稱為「第三方控制」，並且會在使用第三方來連接一對通話者時出現 (例如，操作員安排從人員 A 接到人員 B 的通話)。  <br/> |
|啟用媒體旁路  <br/> |EnableBypass  <br/> |指出是否已針對此主幹啟用媒體旁路。 只有在已啟用**集中媒體處理**的情況中, 才能啟用媒體旁路功能。 <br/> |
|中央媒體處理  <br/> |ConcentratedTopology  <br/> |指出是否有已知的媒體端接點。 (舉例來說，PSTN 閘道就是已知的媒體終端點，其中媒體終端的 IP 與訊號終端相同)。  <br/> |
|啟用 RTP 閉鎖  <br/> |EnableRTPLatching  <br/> |指出 SIP 主幹是否支援 RTP 鎖定。 RTP 鎖定是可以透過 NAT (網路位址轉譯器) 裝置或防火牆進行 RTP/RTCP 連線的技術。  <br/> |
|啟用轉寄通話記錄  <br/> |ForwardCallHistory  <br/> |指出是否透過主幹轉送通話記錄資訊。  <br/> |
|啟用前 P 斷言身分識別資料  <br/> |ForwardPAI  <br/> |指出 P-Asserted-Identity (PAI) 標頭是否要隨通話轉接。 PAI 標頭可用於驗證來電者的身分識別。  <br/> |
|啟用輸出路由容錯移轉計時器  <br/> |EnableFastFailoverTimer  <br/> |指出閘道不會在10秒內接聽的出站通話, 會路由至下一個可用的幹線;如果沒有其他 trunks, 則會自動放棄通話。 組織的網路速度與閘道回應速度若是很慢，可能會造成來電不必要地遭到掛斷。  <br/> |
|關聯的 PSTN 用法  <br/> |PSTNUsages  <br/> |指派給主幹的 PSTN 使用方式集合。  <br/> |
|要測試的已翻譯數位  <br/> |N/A  <br/> |可用於對主幹設定設定執行點對點測試的電話號碼。  <br/> |
|關聯的翻譯規則  <br/> |OutboundTranslationRulesList  <br/> |電話號碼轉譯規則的集合, 這些規則會套用至由輸出路由 (路由至 PBX 或 PSTN 目的地) 所處理的通話。  <br/> |
|呼叫編號轉譯規則  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |指派給主幹的撥出電話號碼轉譯規則集合。  <br/> |
|要測試的電話號碼  <br/> |N/A  <br/> |可用於對翻譯規則進行特殊測試的電話號碼。  <br/> |
|通話號碼  <br/> |N/A  <br/> |表示要測試的電話號碼為來電者的電話號碼。  <br/> |
|叫用號碼  <br/> |N/A  <br/> |表示要測試的電話號碼是呼叫者的電話號碼。  <br/> |
   
> [!NOTE]
> 商務用 Skype Server New-cstrunkconfiguration Cmdlet 支援不會顯示在商務用 Skype Server [控制台] 中的其他屬性。 如需詳細資訊, 請參閱[新版-new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/new-cstrunkconfiguration?view=skype-ps) Cmdlet 的說明主題。
  
### <a name="to-create-new-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 建立新的主幹設定設定

1. 在商務用 Skype Server 的 [控制台] 中, 按一下 [**語音路由**], 然後按一下 [**幹線配置**]。
    
2. 在 [**幹線**設定] 索引標籤上, 按一下 [**新增**], 然後按一下 [**網站主幹**], 在網站範圍建立新的設定, 或 [**池幹線**], 在服務範圍建立新的設定。
    
3. 在 [**選取網站**] 或 [**選取服務**] 對話方塊中 (出現的對話方塊會視您建立的是網站範圍或服務範圍的設定而定) 選取新配置設定的位置, 然後按一下 **[確定]** 。. 如果對話方塊是空白的, 則表示沒有任何位置可供您建立新的設定;例如, 如果 [**選取網站**] 對話方塊為空白, 表示您的所有網站都已指派中繼設定網站集合, 而每個網站 (以及每個服務) 只能託管一個此類集合。 在這種情況下, 您可以刪除現有的集合並建立新的集合, 或只修改現有的集合。
    
4. 在 [**新幹線**設定] 對話方塊中, 進行適當的選取, 然後按一下 **[確定]**。
    
5. 集合的**State**屬性會更新為**未提交**。 若要確認變更, 並刪除收藏, 請按一下 [**認可**], 然後按一下 [**全部確認**]。
    
6. 在 [**未提交的語音設定**] 對話方塊中, 按一下 **[確定]**。
    
7. 在**商務用 Skype Server**的 [控制台] 對話方塊中, 按一下 **[確定]**。
    

