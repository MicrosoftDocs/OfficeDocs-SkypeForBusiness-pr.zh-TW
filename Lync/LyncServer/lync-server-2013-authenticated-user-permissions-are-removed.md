---
title: Lync Server 2013：已移除已驗證的使用者許可權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cf9f63fbe5340b3a241fc60b8623f54906dd8cc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515760"
---
# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>已在 Lync Server 2013 中移除已驗證的使用者許可權

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在鎖定的 Active Directory 環境中，會從預設 Active Directory 容器 (包括「使用者」、「設定」或「系統」，以及儲存「使用者」和「電腦」物件的組織單位 (OU)) 中移除已驗證的使用者存取控制項目 (ACE)。 移除已驗證的使用者 ACE，可防止對 Active Directory 資訊進行讀取存取。 不過，移除 Ace 會產生 Lync Server 2013 的問題，因為此 Ace 取決於這些容器的讀取權限，可讓使用者執行網域準備作業。

在此情況下，Domain Admins 群組的成員資格 (執行網域準備、伺服器啟動及集區建立所需的成員資格) 就不會再授與預設容器中所儲存 Active Directory 資訊的讀取存取權。您必須手動授與樹系根網域中各種容器的讀取存取權限，才能檢查必要的樹系準備程序是否完成。

若要啟用使用者，以便在任何非樹系根網域上執行網域準備、伺服器啟動或集區建立作業，您有以下的選項：

  - 使用屬於 Enterprise Admins 群組成員的帳戶來執行網域準備作業。

  - 使用為 Domain Admins 群組成員的帳戶，並將樹系根網域中下列每個容器的讀取存取權限授與此帳戶：
    
      - 網域
    
      - 設定或系統

如果您不想要使用屬於 Enterprise Admins 群組成員的帳戶來執行網域準備或其他設定工作，請將樹系根中相關容器的讀取存取權明確授與想要使用的帳戶。

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>將樹系根網域中容器的讀取存取權限授與使用者

1.  使用屬於樹系根網域之 Domain Admins 群組成員的帳戶，登入已加入樹系根網域的電腦。

2.  為樹系根網域執行 adsiedit.msc。
    
    如果已從「網域」、「設定」或「系統」容器中移除已驗證的使用者 ACE，則必須授與容器的唯讀權限 (如下列各步驟所述)。

3.  用滑鼠右鍵按一下容器，然後按一下 **[內容]**。

4.  按一下 **[安全性]** 索引標籤。

5.  按一下 [進階]****。

6.  在 [使用權限]**** 索引標籤上，按一下 [新增]****。

7.  使用下列格式，輸入要接收許可權的使用者或群組名稱：，然後 `domain\account name` 按一下 **[確定]**。

8.  在 **[物件]** 索引標籤的 **[套用到]** 中，按一下 **[只有此物件]**。

9.  在 **[使用權限]** 中，按一下 **[允許]** 欄以選取下列「允許 ACE」：**[清單內容]**、**[讀取全部內容]** 和 **[讀取權限]**。

10. 按兩次 **[確定]**。

11. 針對步驟 2 中列出的任何相關容器，重複執行上述步驟。

</div>

</div>

<span> </span>

</div>

</div>

</div>

