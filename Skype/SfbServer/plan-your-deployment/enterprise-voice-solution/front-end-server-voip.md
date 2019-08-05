---
title: 商務用 Skype Server 的前端伺服器 VoIP 元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 瞭解位於商務用 Skype Server 的前端伺服器上的企業語音元件, 包括翻譯服務和各種路由元件。
ms.openlocfilehash: d28beb809e172ea5d778e0cf8273cb232b7cf67c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187687"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>商務用 Skype Server 的前端伺服器 VoIP 元件

瞭解位於商務用 Skype Server 的前端伺服器上的企業語音元件, 包括翻譯服務和各種路由元件。

位於前端伺服器的 VoIP 元件如下所示:

- 翻譯服務

- 入站路由元件

- 輸出路由元件

- Exchange UM 路由元件

- Intercluster 路由元件

- [商務用 Skype Server 中的中繼伺服器元件](mediation-server.md)

## <a name="translation-service"></a>翻譯服務

翻譯服務是一個伺服器元件, 負責根據管理員所定義的正常化規則, 將撥入的號碼翻譯成 E. 164 格式或其他格式。 如果您的組織使用的是私人編號系統, 或使用不支援 E. 164 的閘道或 PBX, 翻譯服務可以翻譯為 E.i 以外的格式。

## <a name="inbound-routing-component"></a>入站路由元件

入站路由元件會根據使用者在企業語音用戶端所指定的喜好設定, 來處理來電的方式。 如果使用者已設定, 它也可協助代理人撥打及同時撥打。 例如, 使用者指定是否已轉寄未接聽的通話, 或只是登入通知。 如果已啟用 [來電轉接], 使用者可以指定是否應將無應答通話轉寄至另一個號碼, 或轉接到已設定為提供呼叫應答的 Exchange UM 伺服器。 入站路由元件預設會安裝在所有標準版伺服器和前端伺服器上。

## <a name="outbound-routing-component"></a>輸出路由元件

輸出路由元件會將呼叫傳送到 PBX 或 PSTN 目的地。 它會將呼叫授權規則 (由使用者的語音原則所定義) 套用至呼叫者, 並決定路由每個通話的最佳 PSTN 閘道。 在所有標準版伺服器和前端伺服器上, 預設會安裝輸出路由元件。

輸出路由元件所使用的路由邏輯, 是根據組織的需求, 由網路或電話系統管理員設定的大型測量。

## <a name="exchange-um-routing-component"></a>Exchange UM 路由元件

Exchange UM 路由元件會處理商務用 Skype 伺服器與執行 Exchange 整合通訊 (UM) 的伺服器之間的路由, 以整合商務用 Skype 伺服器與整合的訊息功能。

如果 Exchange UM 伺服器無法使用, Exchange UM 路由元件也會處理經由 PSTN 的語音信箱重新路由。 如果您在分支網站上有企業語音使用者, 而該使用者沒有指向中央網站的彈性 WAN 連結, 您在分支網站部署的 Survivable 分支裝置會在 WAN 停機期間為分支使用者提供語音信箱留存能力。 WAN 連結無法使用時, Survivable 分支裝置會執行下列動作:

- 將未接聽的電話重新傳送到中央網站的 Exchange 整合訊息伺服器

- 提供使用者在 PSTN 上檢索語音信箱訊息的能力

- 將未接來電通知列隊, 然後在還原 WAN 連結時, 將其上傳到 Exchange UM 伺服器。

若要啟用語音信箱重新路由, 建議您的 Exchange 管理員將 Exchange UM 自動語音應答 (AA) 設定為僅接受郵件。

如需這些功能的詳細資訊, 請參閱[內部部署 Exchange 整合郵件整合](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx)及[企業語音復原規劃](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)。

## <a name="intercluster-routing-component"></a>Intercluster 路由元件

Intercluster 路由元件負責將呼叫路由到被叫方的主要註冊機構池。 如果無法使用, 元件會將呼叫路由到被叫方的備份註冊機構池。 如果被呼叫者的主要和備份註冊器池無法在 IP 網路上使用, 則 Intercluster 路由元件會將呼叫從 PSTN 重新路由到使用者的電話號碼。

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP 所需的其他前端伺服器元件

常駐在前端伺服器或控制器上的其他元件, 可提供 VoIP 的必要支援, 但不是本身的 VoIP 元件, 包括下列各項:

- **使用者服務。** 在每個撥入通話的目的地電話號碼上執行 [反向號碼查閱], 並將該號碼與目的地使用者的 SIP URI 相符。 使用此資訊, 入站路由元件會將呼叫分發給該使用者的已註冊 SIP 端點。 [使用者服務] 是所有前端伺服器和控制器上的核心元件。

- **使用者複製程式。** 從 Active Directory 網域服務提取使用者電話號碼, 並將它們寫入 RTC 資料庫中的資料表, 這些資料可供使用者服務和通訊錄服務器使用。 使用者複製程式是所有前端伺服器上的核心元件。

- **通訊錄服務器。** 提供從 Active Directory 網域服務到商務用 Skype Server 用戶端的全域通訊清單資訊。 它也會從 RTC 資料庫中檢索使用者與連絡人資訊, 並將資訊寫入通訊錄檔案, 然後將檔案儲存在由商務用 Skype 用戶端下載的共用資料夾中。 通訊錄服務器會將資訊寫入 RTCAb 資料庫, 由通訊錄網頁查詢服務用來回應來自商務用 Skype mobile 的使用者搜尋查詢。 它也可以根據在商務用 Skype 中提供使用者連絡人的目的, 將寫入 RTC 資料庫的企業使用者電話號碼標準化。 通訊錄服務預設會安裝在所有前端伺服器上。 預設會安裝通訊錄 Web 查詢服務與每個前端伺服器上的 Web 服務。


