---
title: Lync Server 2013：將 Lync Server 封存原則套用至使用者
description: Lync Server 2013：將 Lync Server 封存原則套用至使用者。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69dcca5601185d65735b963673322a0630af6ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544989"
---
# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a>將 Lync Server 封存原則套用至 Lync Server 2013 中的使用者

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

在建立 Lync Server 使用者原則之後，您必須將其套用至位於 Lync Server 2013 的特定使用者或使用者群組，才會生效。 如需為特定使用者建立使用者原則的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中建立及設定封存的使用者原則](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) 。

如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱規劃檔、部署檔或作業檔中的封存 [在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md) 。

<div>


> [!NOTE]  
> 為了設定和使用封存，您必須先部署封存。 如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-deploying-archiving.md">Lync Server 2013 中部署</A> 封存。<BR>如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 2013 的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。 如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A> 封存的原則。<BR>啟用封存前，應在封存組態中指定所有適當的選項。 如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A> 中設定封存選項。



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a>將 Lync Server 封存原則套用至使用者

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 Lync Server 2013 控制台。 如需可用於啟動 Lync Server 2013 控制台之不同方法的詳細資訊，請參閱 [Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。

5.  在 [封存**原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的封存使用者原則。
    
    <div>
    

    > [!NOTE]  
    > <STRONG> &lt; 自動 &gt; </STRONG>設定會套用預設伺服器安裝設定。 伺服器會自動套用這些設定。

    
    </div>

6.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

