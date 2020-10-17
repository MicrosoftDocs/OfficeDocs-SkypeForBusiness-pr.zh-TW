---
title: Lync Server 2013：設定企業 CA 以進行智慧卡驗證
description: Lync Server 2013：設定企業 CA 以進行智慧卡驗證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98044c96dd04d02fd87609918f309cf65227b133
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548439"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中設定企業 CA 以進行智慧卡驗證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-03_

下列章節說明如何設定企業根憑證授權單位 (CA) 以支援智慧卡驗證。 如需如何安裝企業根 CA 的詳細資訊，請參閱 Install a Enterprise Root 核證機關 at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) 。

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>設定企業根憑證授權以支援智慧卡驗證

下列步驟說明如何設定企業根 CA 以支援智慧卡驗證：

1.  使用網域管理員帳戶登入 Enterprise CA 電腦。

2.  啟動系統管理員，並確認已安裝 [憑證授權單位網站] 註冊角色。

3.  在 [系統 **管理工具** ] 功能表中，開啟 [ **憑證授權單位** 管理主控台]。

4.  在功能窗格中，展開 [ **憑證授權單位**單位]。

5.  以滑鼠右鍵按一下 [ **憑證範本**]，選取 [ **新增**]，然後選取 [ **要發出的憑證範本**]。

6.  選取 [ **註冊代理程式**、 **智慧卡使用者**及 **智慧卡登**入]。

7.  按一下 [確定]****。

8.  以滑鼠右鍵按一下 [ **憑證範本**]。

9.  選取 [ **管理**]。

10. 開啟智慧卡使用者範本的屬性。

11. 按一下 [ **安全性** ] 索引標籤。

12. 變更許可權，如下所示：
    
      - 使用讀取/註冊，新增個別使用者的 AD 帳戶。 (允許) 許可權，或
    
      - 使用讀取/註冊，新增包含智慧卡使用者的安全性群組。 (允許) 許可權，或
    
      - 新增具有讀取/註冊的網域使用者群組 (允許) 許可權

</div>

</div>

<span> </span>

</div>

</div>

</div>

