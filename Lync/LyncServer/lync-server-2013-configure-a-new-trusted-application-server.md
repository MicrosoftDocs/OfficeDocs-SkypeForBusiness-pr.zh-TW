---
title: Lync Server 2013：設定新的受信任的應用程式伺服器
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
ms.openlocfilehash: dae7e02d7642fed5fea60235283eaa0d7d7e1e35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>在 Lync Server 2013 中設定新的受信任應用程式伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

受信任的應用程式是以 microsoft Lync Server 2013 信任的 Microsoft 整合通訊 Managed API （UCMA）3.0 核心 SDK 為基礎的應用程式。 如需有關 UCMA 應用程式的詳細資訊，請參閱「統一通訊管理的[http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)API 3.0 核心 SDK 檔」。

如需有關設定 Microsoft Outlook Web Access （OWA）和 Lync Server 2013 的詳細資訊，請參閱 Microsoft Exchange Server 2013 檔上的「設定 Outlook Web App 和 Lync Server 2010 整合」。

若要在新增或移除伺服器角色時成功發佈、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和網域系統管理員群組成員的使用者身分登入。 您也可以委派適當的管理員許可權與新增伺服器角色的許可權。 如需詳細資訊，請參閱部署檔中的[Lync Server 2013 委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。 針對其他設定變更，只需要 RTCUniversalServerAdmins 群組中的成員資格。

<div>

## <a name="to-configure-a-trusted-application-server"></a>若要設定受信任的應用程式伺服器

1.  登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。

2.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

3.  選取 [**從現有部署下載拓朴**]，然後按一下 **[確定]**。

4.  在 [**另存拓朴為**] 對話方塊中，按一下您要使用的拓撲產生器檔案，然後按一下 [**儲存**]。

5.  在左窗格中，以滑鼠右鍵按一下 [**信任的應用程式伺服器**]，然後按一下 [**新增信任的應用程式池**]。

6.  輸入受信任的應用程式池的 [**池 FQDN** ]，選取它是否為單一伺服器或多重伺服器，然後按 **[下一步]**。

7.  在 [**選取下一個躍點]** 頁面上的清單中，選取 [Lync Server 2013 前端] 池。

8.  按一下 **[完成]**。

9.  選取最上層節點的**Lync Server 2013**，然後從 [**動作**] 功能表中按一下 [**發佈拓撲**]。
    
    **受信任的應用程式池**應該已成功建立，且與正確的 [前端] 池相關聯。

</div>

</div>

<span> </span>

</div>

</div>

</div>

