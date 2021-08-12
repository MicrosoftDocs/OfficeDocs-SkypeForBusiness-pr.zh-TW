---
title: 商務用 Skype Server 的前端伺服器 VoIP 元件
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
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 深入瞭解商務用 Skype Server 中前端伺服器上的企業語音元件，包括轉譯服務和各種路由元件。
ms.openlocfilehash: 5df2937d0329796f634c5b4fac21b6921001d65bf3795589ce718ba08ecd9c36
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333115"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>商務用 Skype Server 的前端伺服器 VoIP 元件

深入瞭解商務用 Skype Server 中前端伺服器上的企業語音元件，包括轉譯服務和各種路由元件。

前端伺服器上的 VoIP 元件如下：

- 轉譯服務

- 輸入路由元件

- 輸出路由元件

- Exchange UM 路由元件

- Intercluster 路由元件

- [商務用 Skype Server 中的轉送伺服器元件](mediation-server.md)

## <a name="translation-service"></a>轉譯服務

「轉譯服務」是負責根據系統管理員定義的正規化規則，將撥打的號碼轉譯成 E.164 格式或其他格式的伺服器元件。如果您的組織使用私人編號系統或使用不支援 E.164 的閘道或 PBX，則「轉譯服務」可以轉譯為 E.164 以外的其他格式。

## <a name="inbound-routing-component"></a>輸入路由元件

輸入路由元件主要會根據使用者在其企業語音用戶端所指定的喜好設定來處理來電。 它也有助於代理人響鈴與同時響鈴 (若使用者已設定) 的使用。 例如，使用者可指定未應答的電話是否要轉接，還是只記錄下來進行通知。 如果已啟用來電轉接，使用者可以指定是否要將未應答的呼叫轉寄到另一個號碼，或是已設定為提供呼叫應答的 Exchange UM 伺服器。 預設會在所有 Standard Edition 伺服器和前端伺服器上安裝輸入路由元件。

## <a name="outbound-routing-component"></a>輸出路由元件

輸出路由元件會將電話路由傳送到 PBX 或 PSTN 目的地。 它會依照使用者的語音原則所定義的呼叫授權規則套用至來電者，並決定用於路由傳送每個通話的最佳 PSTN 閘道。 預設會在所有 Standard Edition 伺服器和前端伺服器上安裝輸出路由元件。

輸出路由元件所使用的路由邏輯會使用大的度量 (由網路或電話語音管理員根據其組織的需求而設定)。

## <a name="exchange-um-routing-component"></a>Exchange UM 路由元件

Exchange UM 路由元件會處理商務用 Skype Server 與執行 Exchange 整合通訊 (UM) 之伺服器之間的路由，以整合商務用 Skype Server 搭配整合通訊功能。

如果無法使用 Exchange um 伺服器，則 Exchange UM 路由元件也會處理透過 PSTN 的語音信箱重新路由。 如果您在分支網站上的企業語音使用者沒有中央網站的彈性 WAN 連結，您在分支網站上部署的 Survivable 分支裝置會在 WAN 中斷期間為分支使用者提供語音信箱留存能力。 當 WAN 連結無法使用時，Survivable 分支裝置會執行下列作業：

- 透過 PSTN，將未接聽的電話重新路由至中央網站的 Exchange Unified Messaging 伺服器

- 提供使用者透過 PSTN 擷取語音信箱訊息的能力

- 將未接來電通知排入佇列，然後在 WAN 連結恢復時將通知上傳至 Exchange UM 伺服器。

為了啟用語音信箱重新路由，我們建議您 Exchange 管理員設定 Exchange UM 自動語音應答 (AA) 只接受郵件。

如需這些功能的詳細資訊，請分別參閱＜[On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration)＞及＜[Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)＞。

## <a name="intercluster-routing-component"></a>Intercluster 路由元件

Intercluster 路由元件負責將通話路由傳送至被呼叫者的主要註冊集區。 如果無法使用該元件，該元件會將通話路由傳送給被呼叫者的備份報名者集區。 如果被呼叫者的主要和備份報名者集區無法透過 IP 網路到達，Intercluster 路由元件會將通話透過 PSTN 重新路由至使用者的電話號碼。

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP 所需的其他前端伺服器元件

位於前端伺服器或 Director 上的其他元件，可為 VoIP 提供必要的支援，但不是本身 VoIP 元件，包括下列各項：

- **使用者服務。** 針對每一來電的目的地電話號碼執行反向號碼查閱，並將該號碼與目的地使用者的 SIP URI 相比對。 使用此資訊，輸入路由元件會將通話散佈給該使用者已註冊的 SIP 端點。 使用者服務是所有前端伺服器及 Director 上的核心元件。

- **使用者複寫器。** 從 Active Directory 網域服務析取使用者電話號碼，並將它們寫入 RTC 資料庫中的表格，以供使用者服務和通訊錄服務器使用。 使用者複製器是所有前端伺服器上的核心元件。

- **Address Book Server。** 將 Active Directory 網域服務的全域通訊清單資訊提供給商務用 Skype Server 用戶端。 它也會從 RTC 資料庫中取得使用者和連絡人資訊，並將資訊寫入通訊錄檔案，然後商務用 Skype 用戶端將檔案儲存在共用資料夾上。 通訊錄服務器會將資訊寫入 RTCAb 資料庫，而通訊錄 Web 查詢服務會使用該資訊，回應使用者搜尋查詢的商務用 Skype 行動。 它會根據在商務用 Skype 中布建使用者連絡人的目的，對寫入 RTC 資料庫的企業使用者電話號碼進行正常化。 預設會在所有前端伺服器上安裝通訊錄服務。 預設會隨每一部前端伺服器上的 Web 服務安裝通訊錄 Web 查詢服務。