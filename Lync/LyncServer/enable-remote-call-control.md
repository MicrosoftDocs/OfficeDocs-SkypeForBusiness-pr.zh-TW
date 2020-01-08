---
title: 啟用遠端通話控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310a140d3497a77ddcaeb8ba32403aa8f28b68e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a>啟用遠端通話控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

[遠端通話控制] 可讓使用者使用 Lync Server 2013 控制其桌面專用分支 exchange （PBX）電話。 如果您在舊版環境中部署遠端通話控制，且想要將它遷移至 Lync Server 2013，您必須執行下列工作：

1.  安裝 SIP/CSTA 閘道，並將它設定為與您的 PBX 進行通訊。 當您部署 Lync Server 2013 試生產池時，必須執行此步驟。

2.  在您合併拓撲並遷移原則和設定之後，請設定 Lync Server 2013，將 CSTA 要求傳送到 SIP/CSTA 閘道。 此步驟是遵循自動遷移的手動步驟。 若要設定 CSTA 要求的路由，請執行下列動作：
    
      - 移除舊版授權主項目目（稱為 Lync Server 2013 中的 [*信任伺服器] 專案*）。 如果您是從舊版部署中遷移使用者，請務必先移除您針對 SIP/CSTA 閘道所建立的所有現有授權主項目目，然後再在 Lync Server 2013 試驗池上設定新的受信任的應用程式專案。 如需如何移除舊版授權主項目目的詳細資料，請參閱[移除授權主項目目](remove-an-authorized-host-entry.md)。
    
      - 設定遠端通話控制的靜態路由。 您可以針對您想要支援遠端呼叫控制的個別池，設定靜態路由，或者您可以設定全域靜態路由，讓未使用池層級靜態路由設定的每個池都使用全域靜態路由。 如需如何設定靜態路由的詳細資料，請參閱部署檔中的[Lync Server 2013 中的 [設定靜態路由以進行遠端通話控制](lync-server-2013-configure-a-static-route-for-remote-call-control.md)]。
    
      - 針對您要支援遠端呼叫控制的每個池，設定受信任的應用程式專案，以進行遠端通話控制。 如需如何設定受信任的應用程式專案的詳細資料，請參閱部署檔中的[Lync Server 2013 中的 [設定信任的應用程式專案](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)]。

3.  如果您已部署使用傳輸控制通訊協定（TCP）連線到 Lync Server 2013 的 SIP/CSTA 閘道，請在 [拓撲建立器] 中定義閘道的 IP 位址。 如需有關定義 IP 位址的詳細資訊，請參閱部署檔中的[Lync Server 2013 中的 [定義 SIP/CSTA 閘道 IP 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)]。

4.  透過啟用遠端呼叫控制並指派線路伺服器統一資源識別項（URI）和行 URI，來設定遠端通話控制的 Lync 2013 使用者。 當您將使用者從舊版部署遷移至 Lync Server 2013 時，遠端通話控制設定會與其他使用者設定一起遷移。

5.  如果您在舊版部署中自訂 [通訊錄電話號碼] 正常化規則，則必須在完成原則和設定的自動遷移之後，執行一些手動工作，才能遷移自訂的正常化規則。 如果您沒有自訂正常化規則，通訊錄會與您的其他拓撲一起遷移。 如需手動遷移自訂正常化規則的詳細資料，請參閱[遷移通訊錄](migrate-address-book_1.md)。

</div>

<span> </span>

</div>

</div>

</div>

