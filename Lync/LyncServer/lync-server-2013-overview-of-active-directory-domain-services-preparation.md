---
title: Lync Server 2013： Active Directory 網域服務準備工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0074b1739cd571db46fc704d4863ac4f0462c99b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500580"
---
# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Lync Server 2013 中的 Active Directory 網域服務準備工作

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

若要為您的 Lync Server 2013 部署準備 Active Directory 網域服務，您必須依特定循序執行三個步驟。

下表說明為 Lync Server 準備 AD DS 所需的步驟。

### <a name="active-directory-preparation-steps"></a>Active Directory 準備步驟

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>步驟</th>
<th>描述</th>
<th>執行位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">在 Lync Server 2013 中準備 Active Directory 架構</a></p></td>
<td><p>新增 Lync Server 所使用的新類別和屬性，以擴充 Active Directory 架構。</p>
<p>針對您要部署 Lync Server 的部署中的每個樹系執行一次。</p></td>
<td><p>針對要部署 Lync Server 之每個樹系的根域中的架構主機。</p>
<div>

> [!NOTE]  
> 如果您擁有架構主機的許可權，您就不需要在根網域中執行這個步驟，但必須是根域中 Schema Admins 群組的成員，以及架構主機上的 Enterprise Admins 群組成員。 在資源樹系拓撲中，僅在資源樹系中執行此步驟，而不是在任何使用者樹系中執行。 在中央樹系拓撲中，請只在中央樹系中執行此步驟，而不是在任何使用者樹系中執行。


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">準備 Lync Server 2013 的樹系</a></p></td>
<td><p>建立 Lync Server 所使用的全域設定與通用群組。</p>
<p>針對您要部署 Lync Server 的部署中的每個樹系執行一次。</p></td>
<td><p>在每個樹系將要部署 Lync Server 的根域中。 您必須是 Enterprise Admins 群組的成員，才可執行此步驟。</p>
<div>

> [!NOTE]  
> 在資源樹系拓撲中，僅在資源樹系中執行此步驟，而不是在任何使用者樹系中執行。 在中央樹系拓撲中，請只在中央樹系中執行此步驟，而不是在任何使用者樹系中執行。


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">準備 Lync Server 2013 的網域</a></p></td>
<td><p>在通用群組的成員要使用的物件上新增許可權。</p>
<p>針對每個使用者網域或伺服器網域執行一次。</p>
<div>

> [!NOTE]  
> 如果您要從 Lync Server 2010 遷移至 Lync Server 2013，部署嚮導可能會指出已完成網域準備工作。 您不需要重新執行網域準備工作。 許可權未從 Lync Server 2010 變更為 Lync Server 2013。


</div></td>
<td><p>在每個將部署 Lync Server 的網域中的成員伺服器上。 您必須是 Domain Admins 群組的成員，才可執行此步驟。</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013 （如 Lync Server 2010）會將許多設定資訊儲存在中央管理存放區中，而不是 Office DS 中，就像是 Office 通訊伺服器 2007 R2 中的案例。 不過，下列資訊會儲存在 AD DS 中：

  - **架構擴充**：
    
      - 使用者物件擴充
    
      - 維護回溯相容性的 Office 通訊伺服器 2007 R2 類別分機

<!-- end list -->

  - 儲存在 Lync Server 擴充架構和現有架構類別中的**資料** () ：
    
      - 使用者 SIP 統一資源識別項 (URI) 和其他使用者設定
    
      - 回應群組和會議助理等應用程式的連絡人物件
    
      - 中央管理存放區的指標
    
      - Kerberos 驗證帳戶 (選用的電腦物件) 

在 Lync Server 2013 中，您可以委派安裝和管理，方法是將設定許可權授與 RTCUniversalServerAdmins 通用群組，讓該群組的成員可以在本機伺服器 (上安裝和啟動 Lync Server 2013，然後再將伺服器新增至拓撲、發行及啟用) 。 委派的使用者必須是安裝和啟動 Lync Server 2013 之電腦上的本機系統管理員，但不需要是 Domain Admins 群組的成員。 您也可以在指定的組織單位 (Ou) 中授與物件的許可權，使樹系準備期間建立的通用群組成員可以存取這些物件，而不是 Domain Admins 群組的成員。

針對 Lync Server 2013 的新部署，全域設定必須儲存在設定容器中。 如果您的組織是從舊版升級，而且您在系統容器內仍有全域設定，系統容器仍然支援。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中準備 Active Directory 架構](lync-server-2013-preparing-the-active-directory-schema.md)  
[Lync Server 2013 使用的 Active Directory 架構擴充功能、類別及屬性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[準備 Lync Server 2013 的樹系](lync-server-2013-preparing-the-forest.md)  
[準備 Lync Server 2013 的網域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

