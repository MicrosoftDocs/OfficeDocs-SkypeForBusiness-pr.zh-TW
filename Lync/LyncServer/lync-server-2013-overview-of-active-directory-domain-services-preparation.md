---
title: Lync Server 2013：Active Directory 網域服務準備工作概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26636846ce7b985a33af3175d51798c4c12c5ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Lync Server 2013 中的 Active Directory 網域服務準備工作概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

若要為您的 Lync Server 2013 部署準備 Active Directory 網域服務，您必須以特定循序執行三個步驟。

下表說明準備 Lync Server 的 AD DS 所需執行的步驟。

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
<th>循序漸進</th>
<th>描述</th>
<th>在何處執行</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">在 Lync Server 2013 中準備 Active Directory 結構描述</a></p></td>
<td><p>新增 Lync Server 所用的新類別和屬性來延伸 Active Directory 架構。</p>
<p>針對您要部署 Lync Server 的部署中的每個林執行一次。</p></td>
<td><p>針對將在其中部署 Lync Server 的每個林的根網域中的架構主機。</p>
<div>

> [!NOTE]  
> 如果您在架構主機上擁有許可權，您就不需要在根網域中執行這個步驟，但您必須是根網域中架構系統管理員群組的成員，以及架構主機上的 [企業系統管理員] 群組的成員。 在資源林拓朴中，請只在資原始目錄林中執行這個步驟，而不是在任何使用者的樹林中執行。 在中央林拓朴中，請只在中央林中執行這個步驟，而不是在任何使用者的樹林中執行。


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">為 Lync Server 2013 準備樹系</a></p></td>
<td><p>建立 Lync Server 所使用的全域設定和通用群組。</p>
<p>針對您要部署 Lync Server 的部署中的每個林執行一次。</p></td>
<td><p>在每個要部署 Lync Server 的林根網域中。 若要執行此步驟，您必須是企業系統管理員群組的成員。</p>
<div>

> [!NOTE]  
> 在資源林拓朴中，請只在資原始目錄林中執行這個步驟，而不是在任何使用者的樹林中執行。 在中央林拓朴中，請只在中央林中執行這個步驟，而不是在任何使用者的樹林中執行。


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">針對 Lync Server 2013 準備網域</a></p></td>
<td><p>在要供通用群組成員使用的物件上新增許可權。</p>
<p>針對每個使用者網域或伺服器網域執行一次。</p>
<div>

> [!NOTE]  
> 如果您是從 Lync Server 2010 遷移到 Lync Server 2013，則 [部署嚮導] 可能會指出已完成 [網域準備]。 您不需要再次執行網域準備。 許可權未從 Lync Server 2010 變更為 Lync Server 2013。


</div></td>
<td><p>在將部署 Lync Server 的每個網域中的成員伺服器上。 若要執行此步驟，您必須是 Domain 系統管理員群組的成員。</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013 （例如 Lync Server 2010）會將許多配置資訊儲存在中央管理儲存體中，而不是在 Office 通訊伺服器 2007 R2 中，而不是在 AD DS 中。 不過，下列資訊會儲存在 AD DS 中：

  - **架構擴充**：
    
      - 使用者物件延伸
    
      - Office 通訊伺服器 2007 R2 類別的延伸，以維持向後相容性

<!-- end list -->

  - **資料**（儲存在 Lync Server 擴展架構和現有的架構類別中）：
    
      - 使用者 SIP 統一資源識別項（URI）及其他使用者設定
    
      - 回應群組和會議助理等應用程式的連絡人物件
    
      - 指向中央管理存放區的指標
    
      - Kerberos 驗證帳戶（選擇性電腦物件）

在 Lync Server 2013 中，您可以將設定許可權授權給 RTCUniversalServerAdmins 通用群組，讓該群組的成員在本機伺服器上安裝並啟用 Lync Server 2013 （在伺服器新增至拓撲、已發佈及已啟用）。 委派的使用者必須是安裝及啟用 Lync Server 2013 之電腦上的本機系統管理員，但不需要成為 Domain Admins 群組的成員。 您也可以在指定的組織單位（Ou）中授與物件的許可權，讓在林準備期間建立的通用群組成員無需成為網域管理員群組的成員，就能存取這些物件。

針對 Lync Server 2013 的新部署，全域設定必須儲存在配置容器中。 如果您的組織是從較舊的版本升級，而且您在系統容器中仍有全域設定，系統容器仍受支援。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中準備 Active Directory 結構描述](lync-server-2013-preparing-the-active-directory-schema.md)  
[Lync Server 2013 使用的 Active Directory 結構描述擴充功能、類別及屬性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[為 Lync Server 2013 準備樹系](lync-server-2013-preparing-the-forest.md)  
[針對 Lync Server 2013 準備網域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

