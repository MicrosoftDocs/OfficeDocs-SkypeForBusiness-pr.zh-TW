---
title: Lync Server 2013：安裝 Lync Server 系統管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8805c82c26eb97da8537b33cda8346f5942de1c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>安裝 Lync Server 2013 系統管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

本主題說明如何安裝您需要用來部署和管理 Lync Server 2013 的系統管理工具。 預設會在每一部執行 Lync Server 2013 的伺服器上安裝系統管理工具。 此外，您也可以在其他電腦上安裝系統管理工具，例如專用的系統管理主控台。 強烈建議您在所建立的 Lync Server 2013 部署所在的電腦上安裝系統管理工具，因為這樣做可以確定 Active Directory 網域服務準備步驟已完成，讓您稍後可以在該電腦上使用系統管理工具發佈拓撲。

在您安裝或使用 Lync Server 2013 系統管理工具之前，請務必先查看基礎結構、作業系統、軟體及系統管理員的許可權需求。 如需基礎結構需求的詳細資訊，請參閱[Lync Server 2013 中的系統管理工具基礎結構需求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。 如需作業系統和軟體需求的詳細資訊，以安裝 Lync Server 2013 系統管理工具，請參閱 lync server [2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)、 [lync server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)，以及[Lync server 2013 中的其他伺服器支援和需求](lync-server-2013-additional-server-support-and-requirements.md)。 如需安裝及使用工具所需之使用者權利的詳細資訊，請參閱[設定和管理 Lync Server 2013 所需的系統管理員許可權](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)。

<div>


> [!IMPORTANT]  
> 如果您的組織需要在系統磁片磁碟機以外的其他磁碟機上找到網際網路資訊服務 (IIS) 和所有 Web 服務，您可以在 [安裝程式] 對話方塊中變更 Lync Server 檔案的安裝位置路徑。 若將安裝檔案安裝至此路徑（包括 OCSCore.msi），則其他的 Lync Server 2013 檔案也會同時部署至此磁片磁碟機。



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>安裝 Lync Server 2013 系統管理工具

1.  以本機系統管理員身分登入，將 (最低需求) 至您要安裝系統管理工具的電腦。 如果您是以 Windows Vista 或 Windows 7 作業系統的標準使用者身分登入，而且使用者帳戶控制權 (UAC) 皆已啟用，系統會提示您輸入本機系統管理員或網域對等的使用者名稱和密碼。

2.  找出電腦上的安裝媒體，然後按兩下 [ \\ Setup \\ amd64Setup.exe] \\ 。

3.  如果系統提示您安裝 Microsoft Visual C++ 2008 可散發套件，請按一下 **[是]**。

4.  在 [ **Microsoft Lync Server 2013 安裝位置**] 頁面上，按一下 **[確定]**。 如果您需要將檔案安裝至其他位置，請將此路徑變更為其他位置或磁碟機。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您的組織需要在系統磁片磁碟機以外的其他磁碟機上找到網際網路資訊服務 (IIS) 和所有 Web 服務，您可以在 [安裝程式] 對話方塊中變更 Lync Server 2013 檔案的安裝位置路徑。 若將安裝檔案安裝至此路徑（包括 OCSCore.msi），則其他的 Lync Server 2013 檔案也會部署至此磁片磁碟機。

    
    </div>

5.  在 **[使用者授權合約]** 頁面上檢閱授權條款，然後依序按一下 **[我接受]** 和 **[確定]**。需要完成此步驟才能繼續。

6.  在 [ **Microsoft Lync Server 2013 –部署嚮導]** 頁面上，按一下 [**安裝系統管理員工具**]。

7.  當安裝順利完成時，按一下 **[結束]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[開啟 Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)  


[Lync Server 2013 系統管理工具](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

