---
title: 檢視 Microsoft SIP Processing Language (MSPL) 伺服器應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2a8aea4b412d2d744c42d659d2414a93c8435e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>在 Lync Server 2013 中檢視 Microsoft SIP Processing Language (MSPL) 伺服器應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-09-26_

Microsoft SIP 處理語言（MSPL）伺服器應用程式是一個只使用指令碼語言的腳本式應用程式，而不是 Microsoft Lync 2010 API。 MSPL 提供對篩選與 proxy 行為的更精細控制，以及將特定訊息分派給事務型 SIP 應用程式的功能。 MSPL 專門用來篩選和路由 SIP 訊息。 MSPL 應用程式在與 UserServices 模組相同的進程中執行，而以 Lync 2010 API 為基礎的程式是在個別的進程中執行。

您可以使用 Lync Server [控制台] 的 [**拓撲**] 群組中的 [**伺服器應用程式**] 頁面，來查看在 Lync server 2013 環境中，在前端伺服器上執行的 MSPL 伺服器應用程式清單。 清單會顯示每個池可用的腳本，以及它們是否已啟用或重要。 腳本會以其列出的循序執行。

這些腳本包括下列各項：

  - ClientVersionFilter 為管理員提供一種方式，以指定池支援的用戶端版本。 用戶端版本篩選會檢查用戶端版本，並可讓用戶端無法登入，或向使用者顯示一則訊息，指出他或她使用的用戶端不受支援。 您也可以設定 [用戶端版本] 篩選器，以向使用者顯示一則訊息，其中包含用戶端最新版下載版本的 URL。

  - TranslationService 會根據管理員所定義的正常化規則，轉譯使用者以164個數字撥號的數位。 如需詳細資訊，請參閱[Lync Server 2013 中的翻譯規則](lync-server-2013-translation-rules.md)。

  - IncomingFederation 會強制執行租使用者層級的同盟驗證與來自外部部署的傳入訊息。

  - UserServices 是前端伺服器的 SIP 註冊機構、目前狀態和會議元件。 它提供了在 SIP Proxy 之上建立的緊密整合 IM、目前狀態及會議功能。

  - InterClusterRouting 負責將呼叫路由到被叫方的主要註冊機構池。 如需詳細資訊，請參閱[Lync server 2013 的前端伺服器 VoIP 元件](lync-server-2013-front-end-server-voip-components.md)。

  - IIMFilter （智慧 IM 篩選器）會封鎖包含可按一下之 Url 或試圖開機檔案傳輸的郵件。 IIMFilter 也會代表伺服器檢查用戶端版本。 IIMFilter 會影響使用 Lync Server 或 Communicator 啟動的檔案傳輸。 根據預設，在連結的第一個字元前面新增一個底線字元，即可停用可按一下的連結。 系統管理員可以變更此行為，讓連結遭到封鎖，在這種情況下，包含可按一下之 Url 的郵件或試圖開機檔案傳輸的訊息，伺服器會封鎖其預定目的地。 在執行 Lync Server 的所有伺服器上，除了 Proxy 伺服器與封存伺服器外，還會安裝 IIMFilter。

  - UserPinService 是用來驗證電話撥入式會議的使用者個人識別碼（Pin）。

  - DefaultRouting 是運行 Lync Server 之伺服器的預設路由應用程式。 預設為啟用。 路由應用程式已安裝在所有標準版和企業版伺服器上。

  - ExumRouting 路由呼叫到 Exchange Server 整合通訊（UM）。 ExumRouting 會決定適當的 Exchange UM 伺服器，以便在有新的語音信箱訊息來存放時傳送通話。 ExumRouting 也會處理一些 Exchange UM 整合的其他方面，包括傳送到自動語音應答及訂閱者存取。

  - OutboundRouting 會根據撥打的號碼和使用者的撥號授權，決定將呼叫路由到電話號碼的閘道。 如果閘道無法處理通話，OutboundRouting 也會處理通話的重新路由。

  - QoEAgent 會透過 SIP 服務要求從端點接收經驗品質（QoE）資料，並將資料傳送到監視伺服器上的目的地佇列，或是使用 HTTP POST 傳送資料給協力廠商消費者。 如需詳細資訊，請參閱[在 Lync Server 2013 中部署監視](lync-server-2013-deploying-monitoring.md)。

  - OutgoingFederation 會強制執行租使用者層級同盟驗證，以取得目標外部部署的訊息。

  - AcpRouting [代理傳送給音訊會議提供者的邀請要求] 到音訊會議提供者閘道。

在邊緣伺服器上執行的腳本包括下列各項：

  - IIMFilter

  - 如果要求是目前伺服器的發件者，則 OptionsHandler 會回應 **[200 確定]** 的傳入選項要求。 這用於拓撲驗證。

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中啟用或停用 Microsoft SIP 處理語言（MSPL）伺服器應用程式](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[在 Lync Server 2013 中將 Microsoft SIP 處理語言（MSPL）應用程式標示為重要或不重要](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

