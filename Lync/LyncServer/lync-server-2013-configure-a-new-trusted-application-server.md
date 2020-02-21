---
title: Lync Server 2013： 設定新的受信任的應用程式伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f4d01e817e1a874af8c6beccdee332f85cc79ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>在 Lync Server 2013 中設定新的受信任的應用程式伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

信任的應用程式是由 Microsoft Lync Server 2013 皆信任的 Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK 為基礎的應用程式。 如需 UCMA 應用程式的詳細資訊，請參閱 「 Unified Communications Managed API 3.0 核心 SDK 文件 」， [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320)。

如需設定 Microsoft Outlook Web Access (OWA) 和 Lync Server 2013 的資訊，請參閱在 Microsoft Exchange Server 2013 文件的 」 設定 Outlook Web App 和 Lync Server 2010 整合 >。

您應以 RTCUniversalServerAdmins 及 Domain Admins 群組成員的身分登入，才能在加入或移除伺服器角色時，成功地發行、啟用或停用拓撲。 另外也可委派適當的系統管理員權限來加入伺服器角色。 如需詳細資訊，請參閱部署文件中的[Lync Server 2013 中的委派設定權限](lync-server-2013-delegate-setup-permissions.md)。 若要進行其他組態變更，則僅需要 RTCUniversalServerAdmins 群組中的成員資格。

<div>

## <a name="to-configure-a-trusted-application-server"></a>若要設定信任的應用程式伺服器

1.  以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。

2.  啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。

3.  選取 **[從現有部署下載拓撲]**，然後按一下 **[確定]**。

4.  在 [**另存拓撲**] 對話方塊中，按一下您要使用拓撲產生器檔案，然後按一下 [**儲存**。

5.  在左窗格中，以滑鼠右鍵按一下 [**信任的應用程式伺服器**，，，然後按一下 [**新增信任的應用程式集區**。

6.  輸入信任的應用程式集區的 [集區 FQDN]****，選擇要讓它成為單一伺服器或多部伺服器，然後按 [下一步]****。

7.  在 [**選取下一個躍點**] 頁面上，從清單中，選取 Lync Server 2013 前端集區。

8.  按一下 [完成]****。

9.  選取頂端節點 [ **Lync Server 2013**中，，然後從 [**動作**] 功能表中，按一下 [**發行拓撲**。
    
    **信任的應用程式集區**應該已成功建立並與正確的前端集區相關聯。

</div>

</div>

<span> </span>

</div>

</div>

</div>

