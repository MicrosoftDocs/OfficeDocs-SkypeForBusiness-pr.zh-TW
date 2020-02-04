---
title: Lync Server 2013：針對智慧卡驗證配置企業 CA
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
ms.openlocfilehash: 44df62031e679c641b4c7dbe6b5c205e1ae899e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中設定智慧卡驗證的企業 CA

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-03_

下列章節說明如何將企業根憑證授權單位（CA）設定為支援智慧卡驗證。 如需如何安裝企業根 CA 的相關資訊，請參閱在[http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)上安裝企業根憑證授權單位。

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>設定企業根憑證授權單位以支援智慧卡驗證

下列步驟說明如何將企業根 CA 設定為支援智慧卡驗證：

1.  使用網域系統管理員帳戶登入企業 CA 電腦。

2.  啟動系統管理員，然後確認已安裝憑證授權單位 Web 登記角色。

3.  從 [**管理工具**] 功能表，開啟 [**認證機構**管理] 主控台。

4.  在 [功能窗格] 中，展開 [**憑證授權單位**]。

5.  以滑鼠右鍵按一下**憑證範本**，選取 [**新增**]，然後選取 [**要頒發的憑證範本**]。

6.  選取 [**註冊代理程式**、**智慧卡使用者**和**智慧卡登**入]。

7.  按一下 [確定]****。

8.  以滑鼠右鍵按一下**憑證範本**。

9.  選取 [**管理**]。

10. 開啟 [智慧卡] 使用者範本的屬性。

11. 按一下 [**安全性**] 索引標籤。

12. 變更許可權，如下所示：
    
      - 新增具有讀取/註冊（允許）許可權的個別使用者廣告帳戶，或
    
      - 新增包含具有讀取/註冊（允許）許可權的智慧卡使用者的安全性群組，或
    
      - 新增具有讀取/註冊（允許）許可權的 [網域使用者] 群組

</div>

</div>

<span> </span>

</div>

</div>

</div>

