---
title: 商務用 SkypeServerModify SIP 主幹設定設定
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'SIP 主幹設定設定定義了轉送伺服器和公用交換電話網路閘道、IP 公用分支 exchange (PBX) 或會話邊界控制器 (SBC) 的服務提供者之間的關聯性和功能。 '
ms.openlocfilehash: ebec5a350dc46a4deb85546e885429ff72737cb2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751722"
---
# <a name="skype-for-business-servermodify-sip-trunk-configuration-settings"></a>商務用 SkypeServerModify SIP 主幹設定設定

SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。這些設定將指定下列項目：

- 主幹是否啟用媒體旁路。
- 傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。
- 每個主幹是否需要安全即時通訊協定 (SRTP) 加密。

當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 主幹設定的集合。 此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。 您可以稍後使用商務用 Skype Server 控制台] 或 Windows PowerShell 來修改這些集合中的任何集合。

使用商務用 Skype Server Server 控制台修改 SIP 主幹設定設定時，您可以使用下列選項：

|UI 設定 |PowerShell 參數 |描述 |
|--|--|--|
|名稱|身分識別|集合的唯一識別碼。此為唯讀屬性，您無法變更主幹組態設定集合的 Identity。|
|描述|描述|為系統管理員提供儲存設定相關資訊 (例如，主幹組態的用途) 的方法。|
|支援的最大早期對話|MaxEarlyDialogs|服務提供者的 PSTN 閘道、IP-PBX 或 SBC 對其傳送到中繼伺服器的 Invite，可接收的分支回應數上限。|
|加密支援等級|SRTPMode|指出支援等級，以保護中繼伺服器和服務提供者之 PSTN 閘道、IP-PBX 或 SBC 之間的媒體流量。 若是媒體旁路的情況，此值必須與媒體組態中的 EncryptionLevel 設定相容。 媒體設定是使用 New-CsMediaConfiguration 和 Set-CsMediaConfiguration Cmdlet 來設定。<br/>允許的值為：<br/><br/>**必要**：必須使用 SRTP 加密。<br/>**選用**：如果閘道支援 SRTP，將會使用。<br/>**不支援**：不支援 SRTP 加密，因此不會使用此加密。<br/><br/>只有閘道設定為使用傳輸層安全性 (TLS) 時，才能使用 SRTPMode。如果將閘道設定為在傳輸時使用傳輸控制通訊協定 (TCP)，系統會從內部將 SRTPMode 設為 Not Supported。|
|轉接支援|Enable3pccRefer<br/>EnableReferSupport|如果設定為 **[啟用傳送轉接至閘道]**，表示主幹支援接收來自中繼伺服器的 Refer 要求。<br/>如果設定為 **[使用協力廠商撥號控制來啟用轉接]**，表示可以使用 3pcc 通訊協定允許轉接通話略過主控網站。3pcc 也稱為「第三方控制」，當使用第三方來連接一組來電者時 (例如，由接線員撥打從 A 到 B 的電話)，就會發生此情況。|
|啟用媒體旁路|EnableBypass|表示此主幹是否啟用媒體旁路。只有在也啟用 **[集中式媒體處理]** 時，才能啟用媒體旁路。|
|集中式媒體處理|ConcentratedTopology|指出是否有已知的媒體終端點 (已知的媒體終端點範例是 PSTN 閘道，其媒體終端的 IP 與訊號終端相同)。|
|啟用 RTP 栓|EnableRTPLatching|指出 SIP 主幹是否支援 RTP 栓。RTP 栓是一種技術，可讓 RTP/RTCP 透過 NAT (網路位址轉譯器) 裝置或防火牆連線。|
|啟用轉接來電記錄|ForwardCallHistory|指出是否將透過主幹來轉接來電記錄資訊。|
|啟用轉寄 P-Asserted-Identity 資料|ForwardPAI|指出 P-Asserted-Identity (PAI) 標頭是否會和通話一起轉寄。PAI 標頭提供確認來電者身分識別的方法。|
|啟用輸出路由容錯移轉計時器|EnableFastFailoverTimer|指出閘道未在 10 秒內接聽的撥出電話將會被路由傳送到下一個可用的主幹；如果沒有其他主幹，就會自動捨棄此電話。在網路和閘道回應速度緩慢的組織中，這可能會造成電話平白遭到捨棄。|
|關聯的 PSTN 使用方式|PSTNUsages|指派給主幹的 PSTN 使用方式集合。|
|要測試的轉譯號碼|不適用|可用於進行主幹組態設定臨機測試的電話號碼。|
|關聯的轉譯規則|OutboundTranslationRulesList|套用到由「輸出路由」處理的電話 (路由傳送到 PBX 或 PSTN 目的地的電話) 的電話號碼轉譯規則集合。|
|撥打號碼轉譯規則|OutboundCallingNumberTranslationRulesList|指派給主幹的撥出電話號碼轉譯規則集合。|
|測試的電話號碼|不適用|可用於進行轉譯規則臨機測試的電話號碼。|
|撥打號碼|不適用|指出要測試的電話號碼是來電者的電話號碼。|
|撥打的號碼|不適用|指出要測試的電話號碼是受話者的電話號碼。|
|||

> [!Note]
> 商務用 Skype Server get-cstrunkconfiguration Cmdlet 支援其他無法在商務用 Skype Server 控制台中顯示的屬性。 如需詳細資訊，請參閱 [Set-CsTrunkConfiguration](/powershell/module/skype/Set-CsTrunkConfiguration) Cmdlet 的 [說明] 主題。 

**使用商務用 Skype Server 控制台修改 SIP 主幹設定設定**

1. 在 [商務用 Skype Server 控制台] 中，按一下 [**語音路由**]，然後按一下 [**主幹** 設定]。
2. 在 [主幹組態] 索引標籤上，連按兩下要修改的主幹組態設定。請注意，一次只能編輯一個集合的設定。如果要針對多個集合進行相同的變更，請改用 Windows PowerShell。
3. 在 [ **編輯主幹** 設定] 對話方塊中，進行適當的選擇，然後按一下 **[確定]**。
4. 集合的 [狀態] 屬性將會更新為 [未認可]。 若要認可變更，並刪除集合，請按一下 [ **認可**]，然後按一下 [ **全部認可**]。
5. 在 [ **未認可的語音設定] 設定** 對話方塊中，按一下 **[確定**]。
6. 在 [**商務用 Skype Server 控制台**] 對話方塊中，按一下 **[確定]**。
