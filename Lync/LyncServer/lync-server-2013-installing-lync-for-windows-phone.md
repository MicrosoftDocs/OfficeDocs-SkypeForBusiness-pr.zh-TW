---
title: Lync Server 2013：安裝 Lync for Windows Phone
description: Lync Server 2013：安裝 Lync for Windows Phone。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f5da90a5dc0babdc6944e4f9c426fe896d4f156
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573979"
---
# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>在 Lync Server 2013 中安裝 Lync for Windows Phone

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-03_

適用于 Windows Phone 的 Lync 2013 是一種可供使用者安裝的應用程式，可在 Windows Phone Marketplace 中使用。

<div>

## <a name="installing-lync-for-windows-mobile"></a>安裝 Lync for Windows Mobile

您可以透過導向使用者至 Windows Phone Marketplace，指示您的使用者在其裝置上安裝 Lync 2013 for Windows Phone <https://go.microsoft.com/fwlink/p/?linkid=231901> 。

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>如果您使用 DNS SRV 記錄發佈 Exchange Web 服務

為了啟用 Lync 用戶端的 Exchange 整合，有些組織會使用 DNS SRV 記錄發佈 Exchange Web 服務 URL。 Microsoft 下載中心提供的檔「瞭解及疑難排解 Exchange 整合」， [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095) 會說明可能需要這種情況的案例。 不過，在此案例中，Windows Phone 使用者的 Exchange 整合不會運作，因為 Windows Phone 平臺不支援 SRV 查閱。 您必須指示 Windows Phone 使用者指定 Exchange Web 服務 URL，而不是讓電話自動偵測到伺服器。

指示您的使用者在其 Windows 電話上設定 Lync 設定，如下所示：

1.  在 [Windows Phone] 的 [Lync 設定] 中，選取 [ **Exchange** ] 畫面。

2.  將 **自動偵測伺服器** 移至 **關閉狀態**。

3.  點擊空白欄位，並輸入 Exchange Web 服務 (FQDN) 或 URL 的完整功能變數名稱。
    
    <div>
    

    > [!NOTE]  
    > 您可以指定完整功能變數名稱 (FQDN) 或您的 Exchange Web 服務伺服器的完整 URL。 如果您指定 FQDN，通訊協定 (HTTPs://) ，且會自動新增 Exchange Web 服務路徑 (/ews/exchange.asmx) 。 如果您的 Exchange Web 服務路徑不同，您可以指定完整的 URL。

    
    </div>

4.  關閉螢幕。

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>確認行動用戶端安裝

在您設定用戶端並登入成功之後，請使用下列測試來確認您的 Lync 2013 安裝在行動裝置上是否正常運作。

**在公司目錄中搜尋連絡人**

1.  在 [連絡人] 清單中，按一下底部的 [ **搜尋** ]。

2.  搜尋只存在於全域通訊清單中的連絡人。

3.  確認連絡人名稱出現在搜尋結果中。

**測試立即訊息和目前狀態**

1.  在 [連絡人] 清單中，按一下連絡人。

2.  在連絡人卡片中，按一下 [ **IM** ] 圖示。

3.  確認立即訊息 (IM) ] 視窗隨即出現，而且您可以輸入及傳送 IM。

**測試電話撥出式會議**

1.  在 Outlook 中，排程 Lync 會議。

2.  在行動裝置上，開啟會議邀請。

3.  按一下會議中的連結以加入。

4.  從會議服務接聽來電，並確認您已連線至會議音訊。

**測試推播通知**

1.  在使用者 A 的行動裝置上，使用使用者 A 的帳戶登入 Lync。

2.  在行動裝置上開啟另一個應用程式。

3.  在不同的用戶端上，使用使用者 B 的帳戶登入 Lync。

4.  從使用者 B 傳送 IM 給使用者 A。

5.  確認 IM 通知出現在使用者 A 的行動裝置上。

</div>

</div>

<span> </span>

</div>

</div>

</div>

