---
title: 在商務用 Skype Server 中修改 SIP 中繼設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
description: 摘要：瞭解如何使用商務用 Skype Server [控制台] 來修改 SIP 幹線設定設定。
ms.openlocfilehash: 137407525319f729eae28d91cfac8cd3aa1b456d
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767096"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中修改 SIP 中繼設定設定
 
**摘要：** 瞭解如何使用商務用 Skype Server [控制台] 來修改 SIP 幹線設定設定。
  
SIP 幹線設定設定會定義在服務提供者上，exchange 中繼伺服器與公用交換式電話網絡（PSTN）閘道、IP 公用分支 eXchange （PBX）或會話邊界控制器（SBC）之間的關聯性與能力。 這些設定會以指定的方式執行以下操作：
  
- 是否應該在 trunks 上啟用媒體旁路。
    
- 傳送即時傳輸控制通訊協定（RTCP）資料包的條件。
    
- 每個幹線是否都需要安全的即時傳輸通訊協定（SRTP）加密。
    
當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 中繼設定。 此外，管理員可以在網站範圍或服務範圍（僅限 PSTN 閘道服務）上建立自訂設定集合。 您可以稍後使用商務用 Skype Server 的 [控制台] 或商務用 Skype Server 管理命令介面來修改這些集合中的任何一個收藏。
  
使用商務用 Skype Server [控制台] 修改 SIP 中繼設定設定時，您可以使用下列選項。
  
|**UI 設定**|**PowerShell 參數**|**說明**|
|:-----|:-----|:-----|
|名稱  <br/> |Identity  <br/> |集合的唯一識別碼。 這個屬性是唯讀的;您無法變更主幹設定集合的身分識別。  <br/> |
|說明  <br/> |說明  <br/> |提供一種方式，讓系統管理員可以儲存有關設定的附加資訊（例如，主幹設定的用途）。  <br/> |
|支援的最大早期對話方塊  <br/> |MaxEarlyDialogs  <br/> |在服務提供者上，PSTN 閘道、IP PBX 或 SBC 的分叉回應數目上限，可能會收到傳送到轉送伺服器的邀請。  <br/> |
|加密支援層級  <br/> |SRTPMode  <br/> | 指示在服務提供者上的中繼伺服器與 PSTN 閘道、IP PBX 或 SBC 之間保護媒體流量的支援層級。 若是媒體旁路的情況，此值必須與媒體組態中的 EncryptionLevel 設定相容。 媒體設定是使用[新的-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmediaconfiguration?view=skype-ps)和[CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) Cmdlet 來設定。 <br/>  允許的值為： <br/>  必要：必須使用 SRTP 加密。 <br/>  [選用]：如果閘道支援，則會使用 SRTP。 <br/>  不支援：不支援 SRTP 加密，因此將無法使用。 <br/>  只有在閘道設定為使用傳輸層安全性（TLS）時，才會使用 SRTPMode。 如果將閘道設定為傳輸控制通訊協定（TCP）作為傳輸，則 SRTPMode 會在內部設定為 [不支援]。 <br/> |
|請參閱支援人員  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |如果設定為**允許傳送參照閘道**，則表示主幹支援從中繼伺服器接收參考要求。  <br/> 如果設定為**啟用 [使用協力廠商通話控制**]，則表示3pcc 通訊協定可以用來允許轉接呼叫繞過託管的網站。 3pcc 亦稱為「第三方控制」，並且會在使用第三方來連接一對通話者時出現 (例如，操作員安排從人員 A 接到人員 B 的通話)。  <br/> |
|啟用媒體旁路  <br/> |EnableBypass  <br/> |指出是否已針對此主幹啟用媒體旁路。 只有在已啟用**集中媒體處理**的情況中，才能啟用媒體旁路功能。 <br/> |
|中央媒體處理  <br/> |ConcentratedTopology  <br/> |指出是否有已知的媒體端接點。 (舉例來說，PSTN 閘道就是已知的媒體終端點，其中媒體終端的 IP 與訊號終端相同)。  <br/> |
|啟用 RTP 閉鎖  <br/> |EnableRTPLatching  <br/> |指出 SIP 主幹是否支援 RTP 鎖定。 RTP 鎖定是可以透過 NAT (網路位址轉譯器) 裝置或防火牆進行 RTP/RTCP 連線的技術。  <br/> |
|啟用轉寄通話記錄  <br/> |ForwardCallHistory  <br/> |指出是否透過主幹轉送通話記錄資訊。  <br/> |
|啟用前 P 斷言身分識別資料  <br/> |ForwardPAI  <br/> |指出 P-Asserted-Identity (PAI) 標頭是否要隨通話轉接。 PAI 標頭可用於驗證來電者的身分識別。  <br/> |
|啟用輸出路由容錯移轉計時器  <br/> |EnableFastFailoverTimer  <br/> |指出閘道不會在10秒內接聽的出站通話，會路由至下一個可用的幹線;如果沒有其他 trunks，則會自動放棄通話。 組織的網路速度與閘道回應速度若是很慢，可能會造成來電不必要地遭到掛斷。  <br/> |
|關聯的 PSTN 用法  <br/> |PSTNUsages  <br/> |指派給主幹的 PSTN 使用方式集合。  <br/> |
|要測試的已翻譯數位  <br/> |不適用  <br/> |可用於對主幹設定設定執行點對點測試的電話號碼。  <br/> |
|關聯的翻譯規則  <br/> |OutboundTranslationRulesList  <br/> |電話號碼轉譯規則的集合，這些規則會套用至由輸出路由（路由至 PBX 或 PSTN 目的地）所處理的通話。  <br/> |
|呼叫編號轉譯規則  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |指派給主幹的撥出電話號碼轉譯規則集合。  <br/> |
|要測試的電話號碼  <br/> |不適用  <br/> |可用於對翻譯規則進行特殊測試的電話號碼。  <br/> |
|通話號碼  <br/> |不適用  <br/> |表示要測試的電話號碼為來電者的電話號碼。  <br/> |
|叫用號碼  <br/> |不適用  <br/> |表示要測試的電話號碼是呼叫者的電話號碼。  <br/> |
   
> [!NOTE]
> Lync Server New-cstrunkconfiguration Cmdlet 支援其他無法在 Lync Server [控制台] 中顯示的屬性。 如需詳細資訊，請參閱[new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cstrunkconfiguration?view=skype-ps) Cmdlet 的說明主題。
  
### <a name="to-modify-sip-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 修改 SIP 幹線設定設定

1. 在商務用 Skype Server 的 [控制台] 中，按一下 [**語音路由**]，然後按一下 [**幹線配置**]。
    
2. 在 [**幹線**設定] 索引標籤上，按兩下要修改的幹線設定設定。 請注意，您只可以一次編輯一個設定集合。 如果您想要對多個集合進行相同的變更，請改為使用 Windows PowerShell。
    
3. 在 [**編輯主幹**設定] 對話方塊中，進行適當的選取，然後按一下 **[確定]**。
    
4. 集合的**State**屬性會更新為**未提交**。 若要確認變更，並刪除收藏，請按一下 [**認可**]，然後按一下 [**全部確認**]。
    
5. 在 [**未提交的語音設定**] 對話方塊中，按一下 **[確定]**。
    
6. 在**商務用 Skype Server**的 [控制台] 對話方塊中，按一下 **[確定]**。
    

