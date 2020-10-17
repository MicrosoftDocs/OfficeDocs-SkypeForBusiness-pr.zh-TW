---
title: Lync Server 2013：設定 AD FS 2.0 以支援用戶端驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d2b713d109a72431e78e966258a84c084523a7a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517640"
---
# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>設定 AD FS 2.0 以支援 Lync Server 2013 中的用戶端驗證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-03_

有兩種可能的驗證類型可設定為允許 AD FS 2.0 支援使用智慧卡的驗證：

  - 以表單為基礎的驗證 (FBA) 

  - 傳輸層安全性用戶端驗證

使用以表單為基礎的驗證，您可以開發一個網頁，讓使用者可以使用其使用者名稱/密碼或使用智慧卡和 PIN 碼進行驗證。 本主題著重于如何使用 AD FS 2.0 來執行傳輸層安全性用戶端驗證。 如需 AD FS 2.0 驗證類型的相關資訊，請參閱 AD FS 2.0：如何變更本機驗證類型 [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384) 。

<div>


**設定 AD FS 2.0 以支援用戶端驗證**

1.  使用網域系統管理員帳戶登入 AD FS 2.0 電腦。

2.  啟動 Windows Explorer。

3.  流覽至 C： \\ inetpub \\ adfs \\ ls

4.  請備份現有的 web.config 檔。

5.  使用 [記事本] 開啟現有的 web.config 檔案。

6.  從功能表列中，選取 [ **編輯** ]，然後選取 [ **尋找**]。

7.  搜尋 **\<localAuthenticationTypes\>** 。
    
    請注意，列出了四種驗證類型，每行一個。

8.  將包含 TLSClient 驗證類型的行移至區段中清單的頂端。

9.  儲存並關閉 web.config 檔案。

10. 以較高的許可權啟動命令提示字元。

11. 執行下列命令以重新啟動 IIS：
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

