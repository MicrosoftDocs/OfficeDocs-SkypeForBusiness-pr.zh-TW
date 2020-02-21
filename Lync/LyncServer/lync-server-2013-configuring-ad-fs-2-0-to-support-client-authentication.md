---
title: Lync Server 2013： 設定 AD FS 2.0 以支援用戶端驗證
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
ms.openlocfilehash: c48e474c511fd8d2e4b3e84bea0d74fcfeb650ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>設定 AD FS 2.0 以支援 Lync Server 2013 中的用戶端驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-07-03_

有兩種可能的驗證類型，可以設定為允許支援使用智慧卡驗證的 AD FS 2.0:

  - 表單型驗證 (FBA)

  - 傳輸層安全性用戶端驗證

您可以使用表單型驗證，開發可讓使用者在驗證使用其使用者名稱與密碼，或使用他們智慧卡及 pin 碼的網頁。 本主題著重於如何實作傳輸層安全性用戶端 Authentication with AD FS 2.0。 如需 AD FS 2.0 驗證類型的詳細資訊，請參閱 AD FS 2.0： 如何變更本機驗證類型在[https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384)。

<div>


**若要設定 AD FS 2.0 以支援用戶端驗證**

1.  登入的 AD FS 2.0 使用網域系統管理員帳戶的電腦。

2.  啟動 Windows 檔案總管]。

3.  瀏覽至 c:\\inetpub\\adfs\\ls

4.  讓現有的 web.config 檔案的備份複本。

5.  開啟現有的 web.config 檔案，使用 [記事本]。

6.  從 [功能表] 列中，選取 [**編輯**]，然後選取 [**尋找**。

7.  搜尋**\<localAuthenticationTypes\>**。
    
    請注意，有四種驗證類型所列，每行一個。

8.  移動包含 TLSClient 驗證類型] 區段中的清單頂端的行。

9.  儲存並關閉 web.config 檔案。

10. 啟動命令提示字元中使用提高的權限。

11. 執行下列命令以重新啟動 IIS：
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

