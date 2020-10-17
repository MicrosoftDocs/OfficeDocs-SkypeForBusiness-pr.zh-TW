---
title: 查看 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22a4098ed36be274f31aaeebb381654595884377
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518460"
---
# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>在 Lync Server 2013 中查看 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-09-26_

Microsoft SIP 處理語言 (MSPL) server 應用程式是一種僅限腳本的應用程式，其使用指令碼語言，而不是 Microsoft Lync 2010 API。 MSPL 針對篩選和 proxy 行為提供更細微的控制，除了用於將特定郵件傳送至交易型 SIP 應用程式的工具之外。 MSPL 特別用於篩選和路由 SIP 郵件。 MSPL 應用程式會在與 UserServices 模組相同的進程中執行，而以 Lync 2010 API 為基礎的程式則會在個別的進程中執行。

您可以使用 Lync Server 控制台的**拓撲**群組中的 [**伺服器應用程式**] 頁面，查看您的 lync Server 2013 環境中前端伺服器上執行的 MSPL 伺服器應用程式清單。 清單會顯示每個集區可用的腳本，以及這些腳本是否已啟用或很重要。 腳本會依照列出的循序執行。

這些指令碼包括下列項目：

  - ClientVersionFilter 為系統管理員提供一種方法，用以指定集區支援的用戶端版本。 用戶端版本篩選器會檢查用戶端版本，並可防止用戶端登入或向使用者顯示訊息，指出其使用的是不支援的用戶端。 用戶端版本篩選也可以設定為向使用者顯示一則訊息，該使用者包含最新可下載版本用戶端的 URL。

  - TranslationService 會轉譯使用者根據系統管理員所定義的正規化規則，撥打 e.164 號碼的數位。 如需詳細資訊，請參閱 [Lync Server 2013 中的轉譯規則](lync-server-2013-translation-rules.md)。

  - IncomingFederation 會針對租使用者和來自外部部署的內送郵件，強制執行租使用者層級的同盟驗證。

  - UserServices 是前端伺服器的 SIP 註冊、目前狀態及會議元件。 它提供了緊密整合的 IM、目前狀態及會議功能（建立于 SIP Proxy 之上）。

  - InterClusterRouting 負責將通話路由傳送至被呼叫者的主要註冊集區。 如需詳細資訊，請參閱 [Lync server 2013 的前端伺服器 VoIP 元件](lync-server-2013-front-end-server-voip-components.md)。

  - IIMFilter (智慧 IM 篩選) 會封鎖包含可按一下 URLs 或嘗試初始化檔案傳輸的郵件。 IIMFilter 也會代表伺服器檢查用戶端版本。 IIMFilter 會影響使用 Lync Server 或 Communicator 所初始化的檔案傳輸。 根據預設，會在連結的第一個字元之前新增底線字元，以停用可按一下的連結。 管理員可以變更此行為，讓連結遭到封鎖，在這種情況下，包含可按一下的 URLs 或嘗試初始化檔案傳輸的郵件會遭到伺服器封鎖，無法到達其預定目的地。 IIMFilter 已安裝在所有執行 Lync Server 的伺服器上，但 Proxy 伺服器和封存伺服器除外。

  - UserPinService 用於驗證使用者個人識別碼 (Pin 碼) 的電話撥入式會議。

  - DefaultRouting 是執行 Lync Server 之伺服器的預設路由應用程式。 預設為啟用。 路由應用程式安裝在所有的 Standard Edition 和 Enterprise Edition server 上。

  - ExumRouting 將通話路由傳送至 Exchange Server 整合通訊 (UM) 。 ExumRouting 會決定當有新的語音信箱訊息要放入時，適當的 Exchange UM 伺服器將通話路由傳送至此。 ExumRouting 也會處理其他一些 Exchange UM 整合的層面，包括路由傳送至自動語音應答和使用者存取。

  - OutboundRouting 會根據撥打的號碼和使用者的撥號授權，決定將通話路由傳送至電話號碼的閘道。 如果閘道無法處理呼叫，OutboundRouting 也會處理呼叫的重新路由。

  - QoEAgent 會收到經驗品質 (QoE 透過 SIP 服務要求從端點) 資料包表，並將資料傳送至監控伺服器上的目的地佇列，或是使用 HTTP POST 將資料傳送至協力廠商消費者。 如需詳細資訊，請參閱 [在 Lync Server 2013 中部署監控](lync-server-2013-deploying-monitoring.md)。

  - OutgoingFederation 會對傳送至目標外部部署的郵件強制執行租使用者層級同盟驗證。

  - AcpRouting proxy 邀請要求的音訊會議提供者到音訊會議提供者閘道的要求。

在 Edge Server 上執行的腳本包括下列各項：

  - IIMFilter

  - OptionsHandler 會回應含 200 OK 的傳入選項要求。如果要求是目前伺服器的目的地，則為 **[確定]** 。 這用於拓撲驗證。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中啟用或停用 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[在 Lync Server 2013 中將 Microsoft SIP 處理語言 (MSPL) 應用程式標示為關鍵或非關鍵](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

