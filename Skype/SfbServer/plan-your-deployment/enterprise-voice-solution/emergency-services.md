---
title: 在商務用 Skype Server 中規劃緊急服務
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: 瞭解商務用 Skype Server Enterprise Voice 中的增強型9-1-1 （E9-1）服務，包括取得位置及呼叫路由。
ms.openlocfilehash: f09729bc6fdbd2fa64dee5b30af88494cd618915
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802983"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃緊急服務

瞭解商務用 Skype Server Enterprise Voice 中的增強型9-1-1 （E9-1）服務，包括取得位置及呼叫路由。

商務用 Skype 伺服器支援在美國內加強9-1-1 （E9-1）服務，成為企業語音部署的一部分。 E9-1-1 是一個緊急派單功能，它會將9-1-1 通話與由市政（也就是街道）位址及其他更多特定位置資訊（例如底價編號）組成的緊急回應位置（例如，來自 office 建築物的通話）進行關聯以及其他多租戶功能。 透過使用隨附的 ERL，公用安全應答點（PSAP）可立即在 distress 中將第一次回應程式傳送給來電者，但不小心會將回應方定向到不正確或不明確的位置。

> [!NOTE]
> 商務用 Skype 伺服器現在支援設定用戶端的多個緊急電話號碼。 如需詳細資訊，請參閱[規劃商務用 Skype Server 中的多個緊急電話號碼](multiple-emergency-numbers.md)。

> [!NOTE]
> 商務用 Skype 伺服器有三個高級企業語音功能： [通話許可控制]、[緊急服務] （E9-1-1），以及 [媒體旁路]。 如需這三個功能共有的規劃資訊的概覽，請參閱[商務用 Skype Server 中的 [高級企業語音功能] 的網路設定](network-settings-for-advanced-features.md)。

商務用 skype Server 支援增強9-1-1 （E9-1-1）從商務用 Skype 用戶端和 Lync Phone Edition 裝置呼叫。 當您將商務用 Skype Server 設定為 E9-1-1，從商務用 Skype 或 Lync Phone Edition 發出緊急通話，包括來自位置資訊服務資料庫的緊急回應位置（ERL）資訊。 ERLs 是由市政（也就是街道）位址及其他資訊所組成，這些資訊可協助您識別更精確的 office 辦公樓及其他具多租戶功能的位置。 當使用者進行緊急通話時，商務用 Skype 伺服器會透過中繼伺服器傳送呼叫音訊，以及位置和回撥資訊，以及在 E9-1-1 服務提供者之間進行。 E9-1 服務提供者使用來電者的市政位址，將呼叫路由至提供來電者位置的公用安全應答點（PSAP），然後沿著 PSAP 用來查詢來電者 ERL 的緊急服務查詢鍵（ESQK）傳送通話。

商務用 Skype 伺服器支援兩種方法，可將緊急呼叫路由至 E9-1-1 服務提供者：

- 與合格 E9-1-1 服務提供者的會話初始通訊協定（SIP）中繼連線

- 將緊急位置識別號碼（ELIN）閘道移至公用交換電話（PSTN）的 E9-1-1 服務提供者

當您使用 SIP 幹線 E9-1 服務提供者時，您會將 ERLs 新增至位置資訊服務資料庫，然後根據 E9-1 服務提供者所維護的主要街道位址指南（MSAG）來驗證位置。 如果 E9-1-1 服務提供者收到的通話沒有位置資訊，或有未針對 MSAG 驗證的位置，E9-1-1 服務提供者會將呼叫路由至國內/地區緊急電話回應中心（ECRC），該人員是由經過專門訓練的人員所組成，verbally 取得來電者的位置，並將呼叫手動傳送給適當的 PSAP。 （部分 SIP 幹線 E9-1 服務提供者也會將 PSTN 直向內撥號（已）號碼提供給 ECRC，這會提供路由9-1-1 呼叫的替代方法，如果 SIP 幹線由於任何原因而失敗。）

與 [時間分段（TDM）] 和 [以 IP 為基礎的專用分支 exchange （PBX）] 電話（具有固定位置）不同，商務用 Skype 端點可以是非常行動。 當您部署 E9-1-1 功能時，商務用 Skype 伺服器有助於確保無論來電者位於何處，緊急通話都可以傳送給提供來電者位置的 PSAP。 例如，如果使用者的主要 office 位於華盛頓州的雷蒙德，但使用者是在 Wichita、堪薩斯、SIP 主幹或 PSTN E9-1-1 服務提供者將呼叫傳送給 Wichita 中的 PSAP，但使用者是從分支辦公室中的電腦撥打緊急電話。，而不是在雷德蒙的 PSAP。

當您使用 ELIN 閘道時，您也會將 ERLs 新增至位置資訊服務資料庫，但每個位置也包含一個 ELIN 號碼。 ELIN 號碼會在緊急通話期間變成緊急電話號碼。 接著，您必須確認 PSTN 載波會將 ELINs 上傳到自動位置識別（阿裡）資料庫。

> [!NOTE]
> 商務用 Skype-已連線的類比裝置無法從位置資訊服務接收位置資訊，或傳送位置資訊給 E9-1-1 服務提供者。

 如果您使用 SIP 幹線 E9-1-1 服務提供者選項，且需要從類比電話支援 E9-1-1，您有兩個選項：

- **傳統 PS-阿裡選項**如果您在每個部署類比電話的網站上有本機 PSTN 閘道，且每個類比電話都有，您可以直接使用私人開關/自動位置識別（PS-阿裡）服務提供者來提供類比裝置的位置。 在這種情況下，您可以設定巧盡心思設計的商務用 Skype 語音原則，並將它們指派給類比裝置連絡人物件，讓來自本機閘道的 E9-1 呼叫直接透過當地閘道傳送給提供該網站的 PSTN 提供者（改為將呼叫路由至 E9-1-1 服務提供者 SIP 主幹）。 當緊急通話進入時，PS-阿裡 provider 中與 PSTN 幹線相關的資料庫會將每個類比電話的執行對應到一個物理位置，並提供此位置至 PSAP。 每次將手機移至不同的 ERLs，就必須使用 PS-阿裡服務提供者來更新這些記錄。

- **E9-1-1 服務提供者選項**如果 E9-1 服務提供者支援，您可以使用 E9-1-1 服務提供者註冊類比手機 DIDs 及其對應的 ERLs。 如果提供者從商務用 Skype Server 接收不含 PIDF-LO 資料的呼叫，提供者就能看到在通話方是否有相符的值。 透過使用從其資料庫取得的 ERL，提供者可以自動將緊急呼叫路由至正確的 PSAP，而 PSAP 會收到類比裝置的功能，以及允許 dispatcher 查閱來電者位置的 ESQK 記錄。

如果您使用的是 ELIN 閘道選項，且需要從類比電話支援 E9-1-1，您可以直接使用 PS-阿裡服務提供者來設定類比裝置的位置，如上述第一個選項中所述。

從商務用 Skype Server 的角度來看，E9-1-1 處理常式可以分為兩個階段：

- 階段1：取得位置

- 階段2：傳送緊急通話至 E9-1-1 服務提供者

本節說明這些階段的運作方式。

如果您打算將基礎結構設定為自動偵測用戶端位置，您必須先決定要用哪些網路元素將呼叫者對應到位置。 如需有關可能選項的詳細資訊，請參閱[在商務用 Skype Server 中定義用來判斷位置的網路元素](network-location.md)。

## <a name="acquiring-a-location"></a>擷取位置

在商務用 Skype Server E9 中，每個內部連線的商務用 Skype 或 Lync Phone Edition 用戶端都會主動取得自己的位置。 在 SIP 註冊之後，用戶端會在位置資訊服務（由複製的 SQL Server 資料庫支援的 web 服務）的位置要求中，furnishes 它知道的所有網路連線資訊。 每個中央網站池都有一個位置資訊服務，該服務會使用網路資訊來查詢其記錄中的相符位置。 如果有相符專案，位置資訊服務會傳回用戶端的位置。 如果沒有相符的專案，系統可能會提示使用者手動輸入位置（視位置原則設定而定）。 位置資料會以網際網路工程任務組（IETF）標準化 XML 格式傳回用戶端，稱為「目前狀態資訊資料格式位置」物件（PIDF-LO）。

商務用 Skype 用戶端會在緊急通話中包含 PIDF-LO 資料，而 E9 1-1 服務提供者會使用這項資料來判斷適當的 PSAP，並將該 PSAP 的呼叫路由到正確的 ESQK，這可讓 PSAP dispatcher取得來電者的位置。

下圖顯示商務用 Skype 用戶端如何取得位置（除了協力廠商用戶端 MAC 以位址為基礎的位置方法之外）：

![用戶端如何取得位置圖表](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

若要讓用戶端取得位置，必須執行下列步驟：

1. 系統管理員會使用 network wiremap （將各種類型的網路位址對應至相對應緊急回應位置（ERLs））來填入位置資訊服務資料庫。

2. 如果您使用 SIP 幹線 E9-1 服務提供者，系統管理員會針對由 E9-1 服務提供者所維護的主要街道位址指南（MSAG）資料庫，驗證 ERLs 的市政位址部分。 如果您使用的是 ELIN 閘道，系統管理員會確保 PSTN 載波將 ELINs 上傳到自動位置識別（阿裡）資料庫。

3. 在註冊期間或每當網路變更時，內部連接的用戶端會傳送包含用戶端探索之網路位址的位置要求給位置資訊服務。

4. 位置資訊服務會針對某個位置查詢其已發佈的記錄，如果找到一個相符專案，則會以 PIDF 格式傳回用戶端的 ERL。

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>使用 SIP 幹線進行路由 E9-1-1 通話

使用 SIP 主幹來連線至合格的 E9-1-1 服務提供者，是一種部署 E9-1-1 的方式。 如需使用 ELIN 閘道連線至公用交換電話網絡（PSTN） E9-1-1 服務提供者的詳細資料，請參閱[使用 ELIN 閘道傳送 E9-1 通話](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx)。

下圖顯示當您使用 SIP 幹線與合格的 E9-1 服務提供者時，緊急通話如何從商務用 Skype Server 路由到公用安全應答點（PSAP）。

**透過 SIP 主幹路由 E9-1-1 通話**

![將緊急電話從 Lync Server 路由傳送至 PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

從相容的商務用 Skype 伺服器用戶端發出緊急通話時：

1. 包含位置的 SIP 邀請、來電者的回呼號碼，以及（選擇性）通知 URL 和會議回呼號碼會傳送到商務用 Skype 伺服器。

2. 商務用 Skype Server 符合緊急電話號碼，並將呼叫路由（根據適用位置原則中定義的**PSTN 使用**值），以及從 SIP 主幹移至 E9-1-1 服務提供者。

3. E9-1-1 服務提供者會根據通話隨附的位置，將緊急通話路由到正確的 PSAP。 當用戶端包含具有緊急呼叫的驗證緊急回應位置（ERL）時，提供者會自動將呼叫路由至適當的 PSAP。 如果該位置是由使用者手動輸入，則緊急呼叫回應中心（ECRC）會先 verbally 驗證與來電者之間的位置準確性，然後才會將緊急呼叫傳送至 PSAP。

4. 如果您已設定通知的位置原則，您組織的一個或多個安全主管會傳送特殊的商務用 Skype 緊急通知立即訊息。 此訊息永遠會出現在安全性監察官的畫面上，並包含來電者的名稱、電話號碼、時間和位置，讓安全人員能使用立即訊息或語音來快速回應緊急來電者。

5. 如果您已設定會議的位置原則，且 E9-1-1 服務提供者支援它，就會使用一種單向音訊或雙向音訊，在通話中 conferenced 內部安全服務台。

6. 如果通話過早中斷，PSAP 會使用回呼號碼直接聯絡來電者。

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>使用 ELIN 閘道路由 E9-1-1 來電

整合通訊開啟互通性計畫中的部分合作夥伴會提供合格的緊急位置識別號碼（ELIN）支援的閘道，這可以作為認證的 E9-1-1 服務提供者的 SIP 中繼連線。 ELIN 閘道支援 ISDN 或集中式自動訊息會計（CAMA）連線至公用交換式電話網絡（PSTN）的 E9-1-1 服務。 如需提供 ELIN 閘道及其檔連結的合作夥伴的詳細資訊，請參閱針對商務用 Skype 的 Microsoft Lync 和[電話結構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)[認證的基礎結構](https://go.microsoft.com/fwlink/p/?LinkId=248425)。

就像 SIP 幹線連線至 E9-1 服務提供者，ELIN 閘道也提供將緊急呼叫路由至呼叫者最適當的公用安全應答點（PSAP）的方式，但這些閘道會使用 ELIN 做為位置識別碼。 您可以針對組織中的每個緊急回應位置（ERL）定義 ELINs （如需詳細資訊，請參閱[在商務用 Skype Server 中管理 ELIN 閘道的位置](elin-gateways.md)）。

當您使用 ELIN 閘道進行緊急通話時，您會使用相同的商務用 Skype 伺服器 E9-1-1-1 也就是說，位置資訊服務資料庫供應商務用 Skype 用戶端的位置，而位置原則則可啟用該功能並定義路由。 不過，有了 ELIN 閘道，您需要將 ELINs 新增到位置資訊服務資料庫，然後將 PSTN 載波上傳到自動位置識別（阿裡）資料庫。

當商務用 Skype 用戶端從位置資訊服務取得位置時，位置會包含 ELIN。 在緊急通話期間，ELIN 會隨附于傳送至 ELIN 閘道的位置。 ELIN 閘道會將呼叫識別為緊急通話，並將通話方的號碼與 ELIN 交換。 ELIN 閘道然後將呼叫路由到 PSTN，並將 ELIN 做為通話號碼。 PSTN E9-1-1 提供者會在阿裡 database 中尋找 ELIN，這是主要街道位址指南（MSAG）資料庫的隨附資料庫。 PSTN 接著根據阿裡 lookup 將呼叫傳送到最合適的 PSAP，而 PSAP 會根據阿裡 lookup 將第一個回應程式傳送給來電者的位置。 呼叫號碼會在 ELIN 閘道上緩存，以預先定義的回呼時間長度。 在回撥期間，PSAP 會達到 ELIN 閘道，交換呼叫者的直接撥入撥號（已有）號碼的 ELIN。

ELIN 閘道只支援從貴組織的網路內部進行緊急通話。 它們不支援從您的網路外部發出的緊急通話。

> [!NOTE]
> 如需有關使用 SIP 中繼連線進行緊急通話的詳細資料，請參閱[使用 Sip 幹線路由 E9-1-1 通話](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx)。

下圖顯示當您使用 ELIN 閘道時，緊急通話如何從商務用 Skype 伺服器傳送到 PSAP。

**使用 ELIN 閘道進行路由 E9-1 通話**

![顯示緊急服務通話如何透過中繼伺服器傳送，然後移到緊急服務提供者。 在此之後，您可以選擇是否要將 IM 傳送至現場安全性，以及/或傳回原始來電者的電話。](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. 包含位置的 SIP 邀請、來電者的回呼號碼，以及（選擇性）通知 URL 和會議回呼號碼會傳送到商務用 Skype 伺服器。

2. 商務用 Skype Server 符合緊急號碼，然後將呼叫路由（根據適用位置原則中定義的**PSTN 使用量**值），並傳送到 ELIN 閘道。

3. ELIN 閘道會透過 ISDN 或 CAMA 幹線將呼叫路由至 PSTN。

4. PSTN 會將通話識別為緊急通話，並將其路由至網路中的 E9 選擇性路由器。 E9-1-1 選擇性路由器會在阿裡 database 中尋找來電者的號碼，以取得地理位置。 E9-1-1 選擇性路由器會根據從阿裡 database 檢索到的位置資訊，將呼叫傳送至最適合的 PSAP。

5. 如果您已設定通知的位置原則，您組織的一個或多個安全主管會傳送特殊的商務用 Skype 緊急通知立即訊息。 此訊息永遠會出現在安全性監察官的畫面上，並包含來電者的名稱、電話號碼、時間和位置，讓安全人員能使用立即訊息或語音來快速回應緊急來電者。

6. 如果通話過早中斷，PSAP 會使用 ELIN 直接聯絡來電者。 ELIN 閘道會調換呼叫者所做的 ELIN。


