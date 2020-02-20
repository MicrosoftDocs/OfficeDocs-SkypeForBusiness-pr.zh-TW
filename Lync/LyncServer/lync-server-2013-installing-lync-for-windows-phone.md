---
title: Lync Server 2013： 安裝 Lync for Windows Phone
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
ms.openlocfilehash: e2dcb2b1fdc41d1d4dd9a047eceaba8bcbc2c3ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>安裝 Lync for Lync Server 2013 中的 Windows Phone

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-03_

Lync 2013 for Windows Phone 是 Windows Phone 市集處於可用的使用者安裝應用程式。

<div>

## <a name="installing-lync-for-windows-mobile"></a>安裝 Lync for Windows Mobile

您可以指示使用者導向至 Windows Phone 市集其裝置上安裝 Lync 2013 for Windows Phone <https://go.microsoft.com/fwlink/p/?linkid=231901>。

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>如果您使用 DNS SRV 記錄來發佈 Exchange Web 服務

若要啟用 Exchange 整合的 Lync 用戶端，有些組織會使用 DNS SRV 記錄來發佈 Exchange Web 服務 URL。 文件 」 了解和疑難排解 Exchange 整合，「 Microsoft 下載中心提供[https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095)，描述在其中這可能需要的案例。 不過，Exchange 整合的 Windows Phone 使用者將無法運作在此案例中，因為在 Windows Phone 平台不支援 SRV 查閱。 您將需要指示 Windows Phone 使用者指定的 Exchange Web 服務 URL 而不讓電話會自動偵測到伺服器。

指示使用者在其 Windows Phone 上設定 Lync 設定如下：

1.  在 Windows Phone Lync 設定中，選取 [ **Exchange** ] 畫面。

2.  將**自動偵測伺服器**移至**關閉**。

3.  點選 [空白欄位，然後輸入完整的網域名稱 (FQDN) 或 Exchange Web 服務的 URL。
    
    <div>
    

    > [!NOTE]  
    > 您可以指定完整的網域名稱 (FQDN) 或 Exchange Web 服務伺服器的完整 URL。 如果您指定的 FQDN、 通訊協定 (https://) 和 Exchange Web 服務路徑 (/ ews/exchange.asmx) 會自動加入。 如果您的 Exchange Web 服務路徑不同，您可以指定完整的 URL。

    
    </div>

4.  關閉 [] 畫面。

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>確認行動用戶端安裝

設定用戶端並登入成功之後，使用下列測試來確認 Lync 2013 的安裝行動裝置上正確運作。

**搜尋在公司目錄中的連絡人**

1.  在 [連絡人] 清單中，點選 [底部的 [**搜尋**]。

2.  搜尋只存在於全域通訊清單的連絡人。

3.  確認連絡人名稱出現在搜尋結果中。

**測試 im 和目前狀態**

1.  在 [連絡人] 清單中，點選 [連絡人]。

2.  連絡人卡片中點選**IM**圖示。

3.  請確認立即訊息 (IM) 視窗隨即出現，而且您可以輸入及傳送 IM。

**測試電話撥出式會議**

1.  在 Outlook 中，排程 Lync 會議。

2.  在行動裝置上，開啟會議邀請。

3.  按一下會議中的連結以加入。

4.  從會議服務接聽來電，並確認您已連線至會議音訊。

**測試推入通知**

1.  在使用者 A 的行動裝置上登入 Lync 使用者 A 的帳戶。

2.  開啟 [行動裝置上的另一個應用程式]。

3.  在不同的用戶端上登入 Lync 使用者 B 的帳戶。

4.  從使用者 B 傳送 IM 給使用者 a。

5.  確認 IM 通知出現在使用者 A 的行動裝置上。

</div>

</div>

<span> </span>

</div>

</div>

</div>

