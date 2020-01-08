---
title: Lync Server 2013：準備 Active Directory 結構描述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5479bfbb0774ddd68015de470de082f0cc185b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>在 Lync Server 2013 中準備 Active Directory 結構描述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-27_

在您開始準備 Active Directory 網域服務之前，您可以使用文字編輯器（例如 Windows Notepad）來開啟架構檔案，或參閱 Lync Server 2013 用來檢查將針對 Lync Server 2013 進行修改之所有 Active Directory 網域服務架構擴充的[Active directory 架構副檔名、類別及屬性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)。 Lync Server 使用四個架構檔：

  - ExternalSchema，用於與 Microsoft Exchange Server 的互通性

  - ServerSchema，這是主要的 Lync Server 2013 架構檔

  - BackCompatSchema，可用於與先前版本中的任何元件進行互通性

  - VersionSchema，用於預準備架構的版本資訊

所有的 .ldf 檔案都會在架構準備期間進行安裝，不論您是從先前的版本進行遷移，還是執行全新安裝。 這些架構檔案是按照前面清單中顯示的順序來安裝，並位於安裝媒體\\上\\的 [支援架構] 資料夾中。

Lync Server 架構擴充功能會在所有網域中複製，這會影響網路流量。 當網路使用量較低時，請一次執行架構準備。

<div>


> [!NOTE]  
> 如果您需要新增 Microsoft® Office Communicator Mobile 2007 R2 for JAVA 及 Microsoft® Office Communicator Mobile for Nokia 1.0 行動用戶端至 Lync Server 2013 部署，您必須準備 Microsoft Office 的 Active Directory 架構在安裝 Lync Server 2013 期間，通訊伺服器 2007 R2。 如需軟體和檔，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>。



</div>

<div>

## <a name="adsi-edit"></a>ADSI 編輯

Active Directory 服務介面編輯器（ADSI 編輯）是一個 AD DS 管理工具，可讓您用來驗證架構準備及複製。

當您安裝 AD DS 角色以使伺服器成為網網域控制站時，預設會安裝 ADSI 編輯。 針對 Windows Server 2008 和 Windows Server 2008 R2，ADSI 編輯（adsiedit）包含在遠端伺服器管理工具（RSAT）中。 您也可以在網域成員伺服器或獨立伺服器上安裝 RSAT。 預設會在您安裝 Windows 時將 RSAT 套件複製到這些伺服器，但預設不會安裝。 您可以使用伺服器管理員安裝個別的工具。 ADSI 編輯包含在**角色管理工具**、 **Active Directory 網域服務工具**、 **active directory 網網域控制站工具**底下。

針對 Windows Server 2003，[支援工具] 附帶 ADSI [編輯]。 支援工具可從 [ \\支援\\工具] 資料夾中的 windows server 2003 光碟取得，您也可以從 [Windows server 2003 Service Pack 2 32-位支援工具] 下載。 [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770) 您可以從「安裝 Windows 支援工具」中取得從產品光碟安裝支援工具的指示[http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)。 當您安裝支援工具時，會自動註冊 Adsiedit .dll。 不過，如果您已將檔案複製到您的電腦，您必須先執行**regsvr32**命令來註冊 adsiedit .dll 檔案，然後才能執行此工具。

</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中執行 Active Directory 架構準備](lync-server-2013-running-schema-preparation.md)

  - [在 Lync Server 2013 中驗證 Active Directory 結構描述複寫](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[為 Lync Server 2013 準備樹系](lync-server-2013-preparing-the-forest.md)  
[針對 Lync Server 2013 準備網域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

