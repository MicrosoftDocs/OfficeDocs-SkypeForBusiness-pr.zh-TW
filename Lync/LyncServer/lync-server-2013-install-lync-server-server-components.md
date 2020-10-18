---
title: Lync Server 2013：安裝 Lync Server 伺服器元件
description: Lync Server 2013：安裝 Lync Server 伺服器元件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1930926f3a46be868d838abf646eb8702c9713a8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574119"
---
# <a name="install-server-components-for-lync-server-2013"></a>安裝 Lync Server 2013 的伺服器元件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-05_

在遵循這些步驟之前，請確定您已使用本機系統管理員和 Active Directory 中的 RTCUniversalReadOnlyAdmins 群組成員的網域使用者帳戶登入伺服器。

Lync Server 部署嚮導是用來安裝每個 Lync server 角色所需的元件，以及啟動伺服器。 本文將引導您逐步完成在 Lync 基礎結構中部署 Standard Edition server 或前端伺服器的步驟。

<div>

## <a name="to-install-lync-server-components"></a>安裝 Lync Server 元件

1.  如果 Lync Server 部署嚮導未執行，請在您想要安裝 Lync 的伺服器上啟動它。

2.  按一下 [ **安裝或更新 Lync Server 系統**]。

3.  在 [部署] 嚮導中，確認 [ **步驟1：安裝本機設定存放區** ] 有綠色核取記號，表示此伺服器已成功安裝存放區的本機複本。 若未勾選，您必須在伺服器上安裝本機設定存放區。 請遵循下列步驟，在 [Lync Server 2013 中安裝本機設定存放區](lync-server-2013-install-the-local-configuration-store.md) ，然後回來回來。

4.  當您準備好在伺服器上安裝 Lync Server 2013 元件時，請按一下 [執行]，然後按一下 [**步驟2：安裝或移除 Lync Server 元件**] 旁邊的 [**執行**]。

5.  在 [ **設定 Lync Server 元件** ] 頁面上，按 **[下一步]** ，依照您已發佈的拓撲中所定義的方式來設定元件。

6.  [ **執行命令** ] 頁面會在設定進行時顯示命令和安裝資訊的摘要。 完成後，您可以使用清單選取要查看的記錄檔，然後按一下 [ **查看記錄**檔]。

7.  在 [Lync Server 2013 元件] 設定完成時，如果您已視需要複查記錄，請按一下 **[完成]** ，以在安裝中完成此步驟。
    
    <div>
    

    > [!NOTE]  
    > 如果系統提示您重新開機伺服器 (可能會在 Windows 桌面經驗安裝) 時進行，因此一定要這麼做。 當電腦重新備份及執行時，您必須重新執行這些步驟，請從上面列出的步驟3開始， (基本上在部署嚮導中執行步驟 2) 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

