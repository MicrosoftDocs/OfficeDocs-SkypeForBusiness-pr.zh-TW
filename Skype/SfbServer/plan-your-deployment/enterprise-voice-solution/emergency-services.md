---
title: 在商務用 Skype Server 中規劃緊急服務
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: 深入瞭解商務用 Skype Server Enterprise Voice 中的增強型 9-1-1 (E9-1-1) 服務，包括位置取得及通話路由。
ms.openlocfilehash: e8eb805a4e4d55f08a4c6aec1a57618c74bcfa02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825763"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃緊急服務

深入瞭解商務用 Skype Server Enterprise Voice 中的增強型 9-1-1 (E9-1-1) 服務，包括位置取得及通話路由。

商務用 Skype 伺服器支援 E9-1-1) 服務中的增強型 (9-1-1，成為企業語音部署的一部分。 E9-1-1 是一種緊急分派功能，它會針對來自辦公大樓或其他多組織用戶共享設備的電話，將 9-1-1 通話與緊急回應位置 (ERL) (包括市鎮 (街道) 地址和其他更明確的位置資訊，例如樓層) 建立關聯。 利用所提供的 ERL，公共安全勤務中心 (PSAP) 可以立即將首先回應者分派給遇難的來電者，以降低誤將回應者導向錯誤或不明位置的風險。

> [!NOTE]
> 商務用 Skype 伺服器現在支援為用戶端設定多個緊急號碼。 如需詳細資訊，請參閱 [在商務用 Skype Server 中規劃多個緊急號碼](multiple-emergency-numbers.md)。

> [!NOTE]
> 商務用 Skype 伺服器具有三個高級 Enterprise Voice 功能：通話許可控制、緊急服務 (E9-1-1) 和媒體旁路。 若要瞭解上述三項功能共同通用的規劃資訊，請參閱 [商務用 Skype Server 中的「高級 Enterprise Voice 功能」網路設定](network-settings-for-advanced-features.md)。

商務用 skype 伺服器支援增強型 9-1-1 (E9-1-1) 呼叫來自商務用 Skype 用戶端和 Lync Phone Edition 裝置。 當您設定 E9-1-1 的商務用 Skype Server，來自商務用 Skype 或 Lync Phone Edition 的緊急通話包含緊急回應位置 (ERL) 位置資訊服務資料庫中的資訊。 Erl 是由市政 (所組成，也就是街道) 位址及其他資訊，可協助識別 office 大樓和其他多租戶設施中的更精確位置。 當使用者進行緊急通話時，商務用 Skype 伺服器會透過轉送伺服器將通話音訊路由傳送至 E9-1-1 服務提供者。 E9-1-1 服務提供者會使用來電者的市政位址，將通話路由傳送至公用安全回應點 (PSAP) 會提供給來電者的位置，並以緊急服務查詢金鑰 (ESQK 一起) 傳送，PSAP 用來查閱來電者的 ERL。

商務用 Skype 伺服器支援將緊急通話路由傳送至 E9-1-1 服務提供者的兩種方法：

- E9-1-1 服務提供者的會話初始通訊協定 (SIP) 主幹連接

-  (PSTN) E9-1-1-1-1-1-1-1-1-1-1-1-1-1-1-1 服務提供者)  (

當您使用 SIP 主幹 E9-1-1 服務提供者時，會將 Erl 新增至位置資訊服務資料庫，然後依照主要街道位址指南 (MSAG) （由 E9-1-1 服務提供者所維護）來驗證位置。 如果 E9-1-1 服務提供者收到的來電沒有位置資訊，或其位置尚未針對 MSAG 驗證，請 E9-1-1 服務提供者會將通話路由傳送到國內/地區緊急通話回應中心 (ECRC) ，其專為訓練有素的人員，其口頭取得來電者的位置，並手動將通話路由到適當的 PSAP。  (某些 SIP 主幹 E9-1-1 服務提供者也會為客戶提供 PSTN direct 向內撥號 (是否) 號碼傳送至 ECRC，如果 SIP 主幹因任何原因而失敗，則會提供另一種路由9-1-1 呼叫的方式。 ) 

不同于時間分割多工 (TDM) 和 IP 型專用交換機 (PBX) 電話（具有固定位置），商務用 Skype 端點可以是非常行動的。 當您部署 E9-1-1 功能時，商務用 Skype 伺服器有助於確保無論來電者位於何處，緊急呼叫都可以路由傳送至服務來電者位置的 PSAP。 例如，如果使用者的主辦公室位於 Redmond，但使用者在 Wichita 中從分公司的電腦撥打緊急電話，則 Kansas 會在 SIP 主幹或 PSTN 型 E9-1-1-1-1-1-1-1-1-1-1-1 服務提供者將通話路由傳送至 Wichita 中的 PSAP

當您使用 ELIN 閘道時，您也可以將 Erl 新增至位置資訊服務資料庫，但也包含每個位置的 ELIN 號碼。 ELIN 號碼會在緊急通話期間成為緊急電話號碼。 接著，您必須確定 PSTN 電信公司將 Elin 上傳至自動位置識別， (阿裡) 資料庫。

> [!NOTE]
> 商務用 Skype 所連線的類比裝置無法從位置資訊服務接收位置資訊，或將位置資訊傳送至 E9-1-1 服務提供者。

 如果您使用 SIP 主幹 E9-1-1 服務提供者選項，且需要從類比電話支援 E9-1-1，您有兩個選項：

- **傳統 PS-ALI 選項** 如果您在每個部署類比電話的網站上都有本機 PSTN 閘道，且每個類比電話都有，您可以直接布建類比裝置的位置，以專用交換機/自動位置識別 (PS-ALI) 服務提供者。 在此情況下，您可以設定巧盡心思構建的商務語音原則，並將它們指派給類比裝置連絡人物件，使來自這些電話的 E9-1-1 呼叫直接路由傳送至 (服務提供者的 PSTN 提供者，而不是將通話路由傳送至 E9-1-1 服務提供者的 SIP 主幹) 。 當緊急通話時，與 PSTN 主幹相關聯之 PS-ALI 提供者的資料庫，會將每個類比電話的執行對應至實體位置，並提供此 PSAP 的位置。 這些記錄必須隨 PS-ALI 服務提供者一起更新，每次行動電話至不同的 Erl。

- **E9-1-1 服務提供者選項** 您可以使用 E9-1-1 服務提供者註冊類比電話 DIDs 及其對應的 Erl （如果 E9-1-1 服務提供者支援此功能）。 如果提供者收到來自商務用 Skype Server 的呼叫，但不包括 PIDF-LO 資料，提供者可以查看在呼叫方的「是否」上存在資料庫是否相符。 透過使用從其資料庫中取得的 ERL，提供者可以自動將緊急通話路由傳送到正確的 PSAP，PSAP 將會收到類比裝置和 ESQK 一起記錄的執行，讓 dispatcher 能夠查閱來電者的位置。

如果您使用 ELIN 閘道選項，且需要支援類比電話的 E9-1-1，您可以直接使用 PS-ALI 服務提供者布建類比裝置的位置，如上述第一個選項所述。

從商務用 Skype Server 的觀點來看，E9-1-1 程式可以分為兩個階段：

- 階段1：取得位置

- 階段2：將緊急通話路由傳送至 E9-1-1 服務提供者

本節說明這些階段的運作方式。

如果您計畫將基礎結構設定為自動偵測用戶端位置，您必須先決定要用來將來電者對應至位置的網路元素。 如需可能選項的詳細資訊，請參閱 [定義用來判斷商務用 Skype Server 中的位置的網路元素](network-location.md)。

## <a name="acquiring-a-location"></a>取得位置

在商務用 Skype Server E9-1-1 部署中，每個內部連線的商務用 Skype 或 Lync Phone Edition 用戶端都會主動取得自己的位置。 在 SIP 註冊後，用戶端會將其本身所知道的所有網路連線資訊 furnishes 至位置資訊服務（即複製的 SQL Server 資料庫所支援的 web 服務）的位置要求。 每個中央網站集區都有一個位置資訊服務，可使用網路資訊來查詢其記錄中的相符位置。 如果有相符的位置資訊服務會將位置傳回用戶端。 如果不符合，系統會提示使用者手動輸入位置 (，視位置原則設定) 而定。 位置資料會傳回網際網路工程工作中的用戶端。 (的 IETF) 標準化 XML 格式，稱為目前狀態資訊資料格式位置物件 (PIDF-LO) 。

商務用 Skype 用戶端在緊急通話中包含 PIDF-LO 資料，而 E9-1-1 服務提供者會使用此資料來判斷適當的 PSAP，並將通話路由傳送至該 PSAP，以及正確的 ESQK 一起，讓 PSAP dispatcher 能夠取得來電者的位置。

下圖顯示商務用 Skype 用戶端如何取得位置 (但協力廠商用戶端 MAC 位址型位置方法) ：

![用戶端如何取得位置圖表](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

若要讓用戶端取得位置，必須進行下列步驟：

1. 系統管理員會以網路線路圖將各種網路位址對應至對應緊急回應位置（ (Erl) # A3）的 [網路] (表格，填入位置資訊服務資料庫。

2. 如果您使用 SIP 主幹 E9-1-1 服務提供者，則系統管理員會依照主要街道位址指南 (MSAG) E9-1-1 服務提供者所維護的資料庫來驗證 Erl 的市政位址部分。 如果您使用的是 ELIN 閘道，則系統管理員會確保 PSTN 載波將 Elin 上傳至自動位置識別 (阿裡) 資料庫。

3. 在註冊期間或網路變更發生時，內部連線的用戶端會傳送包含用戶端已探索網路位址的位置要求至位置資訊服務。

4. 位置資訊服務會查詢其發佈的記錄的位置，如果找到相符的記錄，則會以 PIDF-LO 格式將 ERL 傳回用戶端。

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>使用 SIP 主幹路由傳送 E9-1-1 通話

使用 SIP 主幹來連線到合格的 E9-1-1 服務提供者，是部署 E9-1-1 的方式之一。 如需使用 ELIN 閘道來連線到公用交換電話網路 (PSTN) 型 E9-1-1 服務提供者的詳細資訊，請參閱＜[Routing E9-1-1 Calls by Using an ELIN Gateway](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx)＞。

下圖顯示當您使用 SIP 主幹和合格的 E9-1-1 服務提供者時，緊急通話如何從商務用 Skype Server 路由傳送至公用安全回應點 (PSAP) 。

**透過 SIP 主幹路由傳送 E9-1-1 通話**

![從 Lync Server 到 PSAP 的緊急通話路由](../../media/Plan_LyncServer_E911_CallRouting.jpg)

當緊急通話來自相容的商務用 Skype Server 用戶端時：

1. 包含位置、來電者的回撥號碼，以及 (選用) 通知 URL 和會議回撥號碼的 SIP INVITE 會路由傳送至商務用 Skype Server。

2. 商務用 Skype Server 會比對緊急號碼，並根據在適用位置原則中定義的 **PSTN 使用** 值，) 至轉送伺服器，以及從那裡 E9-1-1 服務提供者的 SIP 主幹來路由傳送通話 (。

3. E9-1-1 服務提供者會依據隨附於通話的位置，將緊急通話路由傳送至正確的 PSAP。當用戶端將驗證過的緊急回應位置 (ERL) 隨附於緊急通話，提供者會自動將通話路由傳送至適當的 PSAP。如果位置是由使用者手動輸入，緊急通話回應中心 (ECRC) 會先向發話者口頭確認位置的精確度，才將緊急通話路由傳送至 PSAP。

4. 如果您已設定通知的位置原則，則會傳送一或多個組織的安全性監察官，以傳送特殊的商務用 Skype 緊急通知立即訊息。 此訊息永遠會在安全性監察官的畫面上彈出 (s) 並包含來電者的名稱、電話號碼、時間和位置，讓安全性人員能夠使用立即訊息或語音，快速回應緊急來電者。

5. 如果您設定了會議的位置原則，且其受到 E9-1-1 服務提供者支援，則內部安全性桌面會以單向音訊或雙向音訊加入電話會議。

6. 如果通話突然中斷，PSAP 會直接使用回撥號碼來連絡發話者。

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>使用 ELIN 閘道路由傳送 E9-1-1 通話

Unified Communications Open Interoperability Program 中的部分合作夥伴會提供具合格緊急位置識別碼 (ELIN) 功能的閘道，對合格的 E9-1-1 服務提供者而言，這些閘道可用來作為 SIP 主幹連線的替代方式。 ELIN 閘道支援 ISDN 或集中式自動訊息記帳 (CAMA) 連線到公用交換電話網路 (PSTN) E9-1-1 服務的功能。 如需提供 ELIN 閘道和其檔連結的合作夥伴詳細資訊，請參閱 Microsoft Lync 和[商務用 Skype 基礎結構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)的[合格基礎結構](https://go.microsoft.com/fwlink/p/?LinkId=248425)。

與 E9-1-1 服務提供者的 SIP 主幹連線，ELIN 閘道也會提供方法，將緊急通話路由傳送至來電者最適當的公用安全回應點 (PSAP) ，但這些閘道使用 ELIN 做為位置識別碼。 您為組織中的每個緊急回應位置 (ERL) 定義 Elin (如需詳細資訊，請參閱 [在商務用 Skype Server) 中管理 ELIN 閘道的位置](elin-gateways.md) 。

當您使用 ELIN 閘道進行緊急通話時，請使用相同的商務用 Skype Server E9-1-1 基礎結構，以用於 SIP 主幹連線。 也就是說，位置資訊服務資料庫會供應商務用 Skype 用戶端的位置，而位置原則會啟用該功能並定義路由。 不過，使用 ELIN 閘道時，您必須將 Elin 新增至位置資訊服務資料庫，並讓 PSTN 電信公司將其上傳至自動位置識別 (阿裡) 資料庫。

當商務用 Skype 用戶端從位置資訊服務取得其位置時，該位置會包含 ELIN。 在緊急通話期間，ELIN 會包含在傳送至 ELIN 閘道的位置中。 ELIN 閘道會將通話識別為緊急通話，並將來電者的號碼更換為 ELIN。 然後 ELIN 閘道會使用 ELIN 作為來電號碼將通話路由傳送至 PSTN。 PSTN E9-1-1 提供者會在 ALI 資料庫中查詢 ELIN，該資料庫是主要街道地址指南 (MSAG) 資料庫的隨附資料庫。 然後 PSTN 會依據 ALI 查詢結果將通話傳送至最合適的 PSAP，PSAP 首先會依據 ALI 查詢結果將回應者傳送至發話方的位置。 在針對回撥預先定義的時間長度內，來電號碼會快取於 ELIN 閘道上。 回撥期間，PSAP 會到達 ELIN 閘道，閘道會將 ELIN 更換為發話方的直接向內撥號 (DID) 號碼。

ELIN 閘道僅支援從您組織的網路內部撥打的緊急通話。 這些閘道不支援從您網路外部撥打的緊急通話。

> [!NOTE]
> 如需針對緊急通話使用 SIP 主幹連線的詳細資訊，請參閱＜[Routing E9-1-1 Calls by Using a SIP Trunk](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx)＞。

下圖顯示當您使用 ELIN 閘道時，緊急通話如何從商務用 Skype Server 路由傳送至 PSAP。

**使用 ELIN 閘道路由傳送 E9-1-1 通話**

![顯示緊急服務通話如何透過轉送伺服器進行，然後再前往緊急服務提供者。 之後，您可以選擇將 IM 傳送至現場安全性，以及/或回撥至原始來電者。](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. 包含位置、來電者的回撥號碼，以及 (選用) 通知 URL 和會議回撥號碼的 SIP INVITE 會路由傳送至商務用 Skype Server。

2. 商務用 Skype Server 會比對緊急號碼，然後根據適用位置原則中所定義的 **PSTN 使用** 方式值，) 至轉送伺服器，以及從那裡傳送至 ELIN 閘道的通話 (。

3. ELIN 閘道會透過 ISDN 或 CAMA 主幹，將通話路由傳送至 PSTN。

4. PSTN 會將該通話識別為緊急通話，並將它路由傳送至網路中 E9-1-1 選擇的路由器。E9-1-1 選擇的路由器會在 ALI 資料庫中查閱來電者的號碼，以取得地理位置。E9-1-1 選擇的路由器會根據從 ALI 資料庫擷取的位置資訊，將通話路由傳送至最適當的 PSAP。

5. 如果您已設定通知的位置原則，則會傳送一或多個組織的安全性監察官，以傳送特殊的商務用 Skype 緊急通知立即訊息。 此訊息永遠會在安全性監察官的畫面上彈出 (s) 並包含來電者的名稱、電話號碼、時間和位置，讓安全性人員能夠使用立即訊息或語音，快速回應緊急來電者。

6. 如果通話提前中斷，PSAP 會使用 ELIN 直接連絡來電者。ELIN 閘道會將 ELIN 更換為來電者的 DID。


