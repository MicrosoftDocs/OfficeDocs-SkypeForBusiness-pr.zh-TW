---
title: Lync Server 2013： 安裝本機設定存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5c95399aa7cccf28ec0c236c2882b6f44794e80
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>在 Lync Server 2013 中安裝本機設定存放區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014 年 06 月 27 日_

執行下列步驟之前，請確定您登入使用網域使用者帳戶是本機系統管理員和擁有 RTCUniversalReadOnlyAdmin 群組成員的伺服器。

若要能夠做任何處理 Lync Server 部署精靈，我們需要存在於伺服器上的本機設定存放區。 本機設定存放區是中央管理存放區，這會取得建立 SQL Server Express 的本機安裝後的唯讀複本。 安裝 Standard Edition server 或 SQL Server Express 式資料庫上的現有 SQL Server 資料庫會加入中央管理存放區本身擷取。

<div>


> [!IMPORTANT]  
> 如果您還沒有執行 Lync Server 2013 安裝程式之前這部伺服器上，系統會提示您的路徑和機安裝 Lync Server 2013。 這可讓您安裝磁碟機以外的系統磁碟機中，如果貴組織需要它，或者如果您有空間考量。 您只可以變更設定] 對話方塊中的 Lync Server 檔案的安裝位置路徑至新的可用的磁碟機。 如果您將安裝檔案安裝到此路徑，包括 OCSCore.msi，Lync Server 2013 檔案的其餘部分將會部署那里也。



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>若要安裝本機設定存放區

1.  從安裝媒體，瀏覽至\\安裝\\amd64\\Setup.exe，然後按一下 [**確定]**。

2.  如果系統提示您安裝 Microsoft Visual c + + 2012年可轉散發套件，按一下 [**是**]。

3.  在**Lync Server 2013 的安裝位置**] 頁面上，按一下 [**確定]**。

4.  在 [**使用者授權合約**] 頁面上，檢閱授權合約，您需要以選取 [**我接受授權合約中的條款**]，然後按一下 **[確定]** 若要能夠繼續。

5.  在 [部署精靈] 頁面上，按一下 [**安裝或更新 Lync Server 系統**]。

6.  在**Lync Server 2013** ] 頁面中下, 一步] 為**步驟 1： 安裝本機設定存放區**，按一下 [**執行**]。

7.  在**安裝本機設定存放區**] 頁面上，請確定已選取 [**直接從中央管理存放區擷取**] 選項，然後再按 [**下一步**。

8.  本機伺服器設定安裝完成時，您應該按一下 [**完成]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

