---
title: Lync Server 2013：安裝 Lync Server 伺服器元件
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
ms.openlocfilehash: 4f039f9363469663410f08f078a3b7e17a170075
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>安裝 Lync Server 2013 的伺服器元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-05_

在遵循這些步驟之前，請確認您已登入的網域使用者帳戶是本機管理員，且在 Active Directory 中是 RTCUniversalReadOnlyAdmins 群組的成員。

Lync Server 部署嚮導是用來安裝每個 Lync 伺服器角色所需的元件，以及啟動伺服器。 本文將引導您逐步完成在 Lync 基礎結構中部署標準版伺服器或前端伺服器的步驟。

<div>

## <a name="to-install-lync-server-components"></a>若要安裝 Lync Server 元件

1.  如果未執行 Lync Server 部署嚮導，請在您要安裝 Lync 的伺服器上啟動。

2.  按一下 [**安裝或更新 Lync Server 系統**]。

3.  在 [部署嚮導] 中，確認 [**步驟1：安裝本機設定儲存區**] 有一個綠色的核取記號，這表示此伺服器已成功安裝該商店的本機複本。 如果未核取，您必須在伺服器上安裝本機配置存放區。 請依照在[Lync Server 2013 中安裝本機設定存儲區中](lync-server-2013-install-the-local-configuration-store.md)的步驟操作，然後回到這裡。

4.  當您準備好要在伺服器上安裝 Lync Server 2013 元件時，請按一下 [步驟2：設定] 旁的 [**執行**]，**或移除 [lync server 元件**]。

5.  在 [**設定 Lync Server 元件**] 頁面上，按一下 **[下一步]** 以設定您在已發佈拓撲中定義的元件。

6.  [**執行命令**] 頁面會在設定發生時顯示命令和安裝資訊摘要。 完成後，您可以使用清單來選取要查看的記錄，然後按一下 [**查看記錄**]。

7.  當 Lync Server 2013 元件設定完成，且您視需要查看記錄時，請按一下 **[完成]** ，以在安裝中完成此步驟。
    
    <div>
    

    > [!NOTE]  
    > 如果系統提示您重新開機伺服器（如果需要安裝 Windows 桌面體驗，可能會發生這種情況），請務必這麼做。 當電腦重新開機並繼續執行時，您需要再次執行這些步驟，從前面所列的步驟3開始（基本上在 [部署嚮導] 中再執行一次步驟2）。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

