---
title: Lync Server 2013：安裝 Lync for Windows Phone
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
ms.openlocfilehash: 75e42f9fd2b954e943050fc9877706ae53a1143c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>在 Lync Server 2013 中安裝 Lync for Windows Phone

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-03_

Windows Phone 適用的 Lync 2013 是 Windows Phone Marketplace 提供的使用者可安裝應用程式。

<div>

## <a name="installing-lync-for-windows-mobile"></a>安裝 Lync for Windows Mobile

您可以透過將 Lync 2013 的裝置導向至 Windows Phone Marketplace，來指示您的使用者在他們的裝置上<http://go.microsoft.com/fwlink/p/?linkid=231901>安裝 Lync For windows phone。

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>如果您使用 DNS SRV 記錄發佈 Exchange Web 服務

若要啟用 Lync 用戶端的 Exchange 整合，有些組織會使用 DNS SRV 記錄來發佈 Exchange Web 服務 URL。 Microsoft 下載中心提供的檔「瞭解及疑難排解 Exchange 整合」 [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)，說明可能需要進行的案例。 不過，Windows phone 版 Exchange 整合使用者無法在這種情況下運作，因為 Windows Phone 平臺不支援 SRV 查閱。 您將需要指示 Windows Phone 使用者指定 Exchange Web 服務 URL，而不是允許手機自動偵測伺服器。

指示您的使用者在其 Windows 手機上設定 Lync 設定，如下所示：

1.  在 Windows Phone 的 Lync 設定中，選取 [ **Exchange** ] 畫面。

2.  將 [**自動偵測伺服器**] 移至 [**關閉**]。

3.  敲擊空白欄位，然後輸入 Exchange Web 服務的完整功能變數名稱（FQDN）或 URL。
    
    <div>
    

    > [!NOTE]  
    > 您可以指定 Exchange Web 服務伺服器的完整功能變數名稱（FQDN）或完整 URL。 如果您指定 FQDN，就會自動新增通訊協定（HTTPs://）和 Exchange Web 服務路徑（/ews/exchange.asmx）。 如果 Exchange Web 服務路徑不一樣，您可以指定完整的 URL。

    
    </div>

4.  關閉螢幕。

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>驗證行動用戶端安裝

在您設定用戶端並成功登入之後，請使用下列測試確認您的 Lync 2013 安裝在您的行動裝置上正常運作。

**在公司目錄中搜尋連絡人**

1.  在 [連絡人] 清單中，按一下底部的 [**搜尋**]。

2.  搜尋僅存在於全域通訊清單中的連絡人。

3.  確認連絡人名稱出現在搜尋結果中。

**測試立即訊息和目前狀態**

1.  在連絡人清單中，輕觸連絡人。

2.  在連絡人卡片中，按一下 [ **IM** ] 圖示。

3.  確認立即訊息（IM）視窗出現，而且您可以輸入並傳送即時消息。

**測試撥出式會議**

1.  在 Outlook 中，排程 Lync 會議。

2.  在行動裝置上，開啟會議邀請。

3.  按一下會議中要加入的連結。

4.  從會議服務接聽通話，並確認您已連線到會議音訊。

**測試推播通知**

1.  在使用者 A 的行動裝置上，使用使用者 A 的帳戶登入 Lync。

2.  在行動裝置上開啟另一個應用程式。

3.  在其他用戶端上，使用使用者 B 的帳戶登入 Lync。

4.  從使用者 B 傳送 IM 給使用者 A。

5.  確認 IM 通知出現在使用者 A 的行動裝置上。

</div>

</div>

<span> </span>

</div>

</div>

</div>

