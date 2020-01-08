---
title: Lync Server 2013：已移除已驗證使用者權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d5e14b8129f771093ed9facb09d047ac7c36d32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>Lync Server 2013 中已移除已驗證使用者權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在鎖定的 Active Directory 環境中，已從預設 Active Directory 容器中移除經過驗證的使用者存取控制專案（Ace），包括使用者、配置或系統，以及使用者和電腦的組織單位（Ou）。儲存物件。 移除經過驗證的使用者 Ace 可防止讀取 Active Directory 資訊的讀取權限。 不過，移除 Ace 會針對 Lync Server 2013 產生問題，因為它依賴于這些容器的讀取權限，以允許使用者執行網域準備。

在這種情況下，網域系統管理員群組中的成員資格是執行網域準備、伺服器啟用和池建立，不會再授與預設容器中所儲存之 Active Directory 資訊的讀取存取權。 您必須在林根網域的各個容器上手動授與存取權，以檢查必備的目錄林準備程式是否已完成。

若要讓使用者在任何非林根網域上執行網域準備、伺服器啟用或池建立，您可以使用下列選項：

  - 使用企業系統管理員群組成員的帳戶來執行網域準備。

  - 使用網域系統管理員群組成員的帳戶，並在林根網域的下列每個容器中，授與此帳戶的讀取存取許可權：
    
      - 主域
    
      - 配置或系統

如果您不想使用企業系統管理員群組成員的帳戶來執行網域準備或其他設定工作，請明確授予您想要在林根的相關容器上使用 [讀取] 存取權的帳戶。

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>在林根網域中為使用者提供對容器的讀取存取許可權

1.  使用屬於林根網域之網域系統管理員群組成員的帳戶登入加入林根網域的電腦。

2.  針對目錄林根網域執行 adsiedit。
    
    如果從 [網域]、[設定] 或 [系統] 容器中移除經過驗證的使用者 Ace，您必須授與容器的唯讀許可權，如以下步驟所述。

3.  以滑鼠右鍵按一下容器，然後按一下 [**屬性**]。

4.  按一下 [**安全性**] 索引標籤。

5.  按一下 [進階]****。

6.  按一下 [**許可權**] 索引標籤上的 [**新增**]。

7.  使用下列格式，輸入接收許可權的使用者或群組的名稱： `domain\account name`，然後按一下 **[確定]**。

8.  在 [**物件**] 索引標籤上的 [**適用**于] 中，按一下 [**僅此物件**]。

9.  在 [**許可權**] 中，按一下 [**允許**] 欄： [**清單內容**]、[**讀取所有屬性**] 和 [**讀取權限**]，以選取下列允許 ace。

10. 按一下 **[確定]** 兩次。

11. 針對步驟2中所列的任何相關容器，重複這些步驟。

</div>

</div>

<span> </span>

</div>

</div>

</div>

