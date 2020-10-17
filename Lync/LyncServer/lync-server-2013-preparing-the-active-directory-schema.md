---
title: Lync Server 2013：準備 Active Directory 架構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27c785596d1fe994e3156eb0e52ed840609a5c26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506850"
---
# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>在 Lync Server 2013 中準備 Active Directory 架構

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-27_

在您開始準備 Active Directory 網域服務之前，您可以使用文字編輯器（例如 Windows Notepad）來開啟架構檔案，或查看 [Lync server 2013 所使用的 Active directory 架構副檔名、類別和屬性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) ，以查看將針對 Lync server 2013 修改的所有 Active Directory 網域服務架構擴充。 Lync Server 使用四個架構檔案：

  - 用於與 Microsoft Exchange Server 進行互通性的 ExternalSchema.ldf

  - ServerSchema.ldf，也就是主要 Lync Server 2013 架構檔案

  - BackCompatSchema.ldf，這個檔案用於提供與任何舊版元件的互通性

  - VersionSchema.ldf，這個檔案用於提供預備架構的版本資訊

不論您是從舊版進行移轉或執行全新安裝，所有 .ldf 檔案都是在架構準備期間進行安裝。 這些架構檔案會依上述清單中顯示的順序安裝，並位於 \\ \\ 安裝媒體上的 [支援架構] 資料夾中。

Lync Server 架構擴充會在所有網域間進行複製，這會影響網路流量。 請在網路使用率較低時執行架構準備作業。

<div>


> [!NOTE]  
> 如果您需要將 Microsoft® Office Communicator Mobile 2007 R2 for JAVA 和 Microsoft® Office Communicator mobile for Nokia 1.0 行動用戶端新增至您的 Lync Server 2013 部署，您必須在安裝 Lync Server 2013 期間，準備好 Microsoft Office 通訊2007伺服器的 Active Directory 架構。 如需必要的軟體及檔，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A> 。



</div>

<div>

## <a name="adsi-edit"></a>ADSI 編輯器

Active Directory 服務介面編輯器 (ADSI 編輯器) 是您可以用於驗證架構準備和複寫的 AD DS 系統管理工具。

當您安裝 AD DS 角色以使伺服器成為網域控制站時，預設會安裝 ADSI 編輯器。 若為 Windows Server 2008 和 Windows Server 2008 R2，ADSI Edit (adsi) 隨附 (RSAT) 的遠端伺服器管理工具。 您也可以在網域成員伺服器或獨立伺服器上安裝 RSAT。 RSAT 套件預設會在您安裝 Windows 時複製到這些伺服器，但並不會進行安裝。 您可以使用伺服器管理員來安裝個別的工具。 「ADSI 編輯器」包含在 **[角色管理工具]**、**[Active Directory 網域服務工具]**、**[Active Directory 網域控制站工具]** 之下。

如果是 Windows Server 2003，ADSI 編輯器包含在支援工具中。 支援工具可在 [支援工具] 資料夾中的 [Windows Server 2003 CD] 中取得 \\ \\ ，您也可以從「windows Server 2003 Service Pack 2 32-位支援工具」下載這些工具 [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770) 。 您可以從「安裝 Windows 支援工具」中取得安裝產品 CD 支援工具的指示 [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771) 。 當您安裝支援工具時，就會自動登錄 Adsiedit.dll。 不過，若您將檔案複製到電腦，則必須先執行 **regsvr32** 命令來登錄 adsiedit.dll 檔案，才能執行該工具。

</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中執行 Active Directory 架構準備](lync-server-2013-running-schema-preparation.md)

  - [在 Lync Server 2013 中驗證 Active Directory 架構複寫](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[準備 Lync Server 2013 的樹系](lync-server-2013-preparing-the-forest.md)  
[準備 Lync Server 2013 的網域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

