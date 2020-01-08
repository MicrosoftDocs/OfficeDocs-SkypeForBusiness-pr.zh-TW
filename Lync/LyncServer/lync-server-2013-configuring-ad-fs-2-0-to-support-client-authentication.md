---
title: Lync Server 2013：設定 AD FS 2.0 以支援用戶端驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12f7cad4b36eb96f7b36925aa91e6363b8cdd264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中設定 AD FS 2.0 以支援用戶端驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-03_

有兩種可能的驗證類型可以設定為允許 AD FS 2.0 使用智慧卡支援驗證：

  - 以表單為基礎的驗證（FBA）

  - 傳輸層安全性用戶端驗證

使用以表單為基礎的驗證，您可以開發網頁，讓使用者可以使用他們的使用者名稱/密碼或使用其智慧卡和 PIN 來進行驗證。 本主題重點說明如何使用 AD FS 2.0 來實現傳輸層安全性用戶端驗證。 如需有關 AD FS 2.0 驗證類型的詳細資訊，請參閱 AD FS 2.0：如何變更本機驗證類型[http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)。

<div>


**設定 AD FS 2.0 以支援用戶端驗證**

1.  使用網域系統管理員帳戶登入 AD FS 2.0 電腦。

2.  啟動 Windows 資源管理器。

3.  流覽至 C：\\inetpub\\adfs\\ls

4.  製作現有 web.config 檔案的備份複本。

5.  使用記事本開啟現有的 web.config 檔案。

6.  從功能表列中，選取 [**編輯**]，然後選取 [**尋找**]。

7.  搜尋** \<localAuthenticationTypes\>**。
    
    請注意，列出四個驗證類型，每行一個。

8.  將包含 TLSClient 驗證類型的行移至區段中清單的頂端。

9.  儲存並關閉 web.config 檔案。

10. 以較高的許可權啟動命令提示字元。

11. 執行下列命令以重新開機 IIS：
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

