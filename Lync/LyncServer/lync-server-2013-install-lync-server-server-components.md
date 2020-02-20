---
title: Lync Server 2013： 安裝 Lync Server 伺服器元件
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
ms.openlocfilehash: b6cb5c895eb58f7839c3e748524d7b355a08daff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>安裝 Lync Server 2013 的伺服器元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-05-05_

執行下列步驟之前，請確定您登入網域使用者帳戶是本機系統管理員和 Active Directory 中的 RTCUniversalReadOnlyAdmins 群組成員的伺服器。

Lync Server 部署精靈用來安裝每個 Lync 伺服器角色的必要的元件以及啟動伺服器。 本文會引導您完成部署 Standard Edition server 或前端伺服器 Lync 基礎結構中的步驟。

<div>

## <a name="to-install-lync-server-components"></a>安裝 Lync Server 元件

1.  如果未執行 Lync Server 部署精靈，請在您想要安裝到 Lync 伺服器上啟動它。

2.  按一下 [**安裝或更新 Lync Server 系統**]。

3.  在 [部署精靈]，確認**步驟 1： 安裝本機設定存放區**有綠色核取記號，表示此伺服器皆已成功安裝的存放區的本機複本。 如果未核取，您需要在伺服器上安裝本機設定存放區。 遵循在[安裝本機設定存放區 Lync Server 2013 中](lync-server-2013-install-the-local-configuration-store.md)的步驟，然後再回來。

4.  當您準備好您的伺服器上安裝 Lync Server 2013 元件時，請按一下 [**執行**下一步] 為**步驟 2： 安裝或移除 Lync Server 元件**。

5.  在 [**設定設定 Lync Server 元件**] 頁面上，按 [**下一步**設定元件，如已發行的拓撲中所定義。

6.  [**執行命令**] 頁面上會顯示命令和安裝資訊的摘要作為進行設定。 完成後，您可以使用清單選取 [記錄] 來檢視，，，然後按一下 [**檢視記錄檔**。

7.  Lync Server 2013 元件安裝完成時，且您已檢閱記錄檔，視需要請按一下 [**完成**] 以完成安裝在此步驟。
    
    <div>
    

    > [!NOTE]  
    > 如果系統提示您重新啟動伺服器 （如果安裝所需的 Windows 桌面體驗，則可能發生），明確地這麼做。 在電腦上一步是啟動並執行，您需要透過一次，請執行下列步驟從步驟 3 上列 (基本上執行步驟 2 中部署精靈一個更多時間) 開始。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

