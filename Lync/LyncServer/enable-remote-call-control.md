---
title: 啟用遠端呼叫控制
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa81c938d69aedbc599194c1d820fa4c40e3337
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502890"
---
# <a name="enable-remote-call-control"></a>啟用遠端呼叫控制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

遠端呼叫控制可讓使用者使用 Lync Server 2013，控制其桌面專用交換機 (PBX) 電話。 如果您已在舊版環境中部署遠端呼叫控制，且想要遷移其 Lync Server 2013，您必須執行下列工作：

1.  安裝 SIP/CSTA 閘道，並將其通訊對象設定成您的 PBX。 當您部署 Lync Server 2013 試驗集區時，您必須執行此步驟。

2.  在您合併拓撲及遷移原則及設定之後，請將 Lync Server 2013 設定為將 CSTA 要求路由傳送至 SIP/CSTA 閘道。 此步驟必須在自動化移轉作業之後手動執行。 若要設定 CSTA 要求的路由，請執行下列動作：
    
      - 在 Lync Server 2013) 中移除舊版授權主項目目 (稱為「 *信任的伺服器」專案* 。 若要從舊版部署遷移使用者，請務必在 Lync Server 2013 試驗集區上設定新的信任應用程式專案之前，先移除為 SIP/CSTA 閘道建立的所有現有授權主項目目。 如需如何移除舊版授權主項目目的詳細資訊，請參閱 [移除授權主項目目](remove-an-authorized-host-entry.md)。
    
      - 設定遠端呼叫控制的靜態路由。 您可以為要支援遠端呼叫控制功能的各集區設定靜態路由，或是設定全域靜態路由，以便於未設定集區等級之靜態路由的各集區可以使用全域靜態路由。 如需如何設定靜態路由的詳細資訊，請參閱部署檔中的 [configure a static route for remote call control In Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) 。
    
      - 為每個想要支援遠端呼叫控制之集區上的遠端呼叫控制，設定信任的應用程式項目。 如需如何設定信任的應用程式專案的詳細資訊，請參閱部署檔中的 [configure a trusted application entry In Lync Server 2013 中的遠端呼叫控制](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) 。

3.  如果您部署了使用傳輸控制通訊協定的 SIP/CSTA 閘道 (TCP) 連接至 Lync Server 2013，請在拓撲產生器中定義閘道的 IP 位址。 如需定義 IP 位址的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) 。

4.  透過啟用遠端呼叫控制，並指派行伺服器統一資源識別項 (URI) 和行 URI，為遠端呼叫控制設定 Lync 2013 使用者。 當您從舊版部署將使用者遷移至 Lync Server 2013 時，遠端呼叫控制設定會隨其他使用者設定一起遷移。

5.  若您的舊版部署中自訂有通訊錄電話號碼正規化規則，必須在自動化移轉原則及設定的作業完成之後，執行一些手動工作，才可移轉自訂的正規化規則。 若您未自訂任何正規化規則，通訊錄將會隨拓撲的剩餘部分一併移轉。 如需手動移轉自訂正規化規則的詳細資訊，請參閱＜[Migrate Address Book](migrate-address-book_1.md)＞。

</div>

<span> </span>

</div>

</div>

</div>

