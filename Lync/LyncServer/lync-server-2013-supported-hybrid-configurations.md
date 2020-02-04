---
title: Lync Server 2013：支援的混合式設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dea28ecfcd5e6a881c1d3d1ee63f16cd4821410
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>支援的 Lync Server 2013 混合式設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-05-10_

您可以設定 Lync Server 2013 部署，以與 Microsoft Exchange Server 2010 以及內部部署和線上的 Microsoft exchange Server 2013 與 SharePoint Server 整合。 除非另外指定，否則所有用戶端都支援下表所列的功能。 如需用戶端支援的詳細資訊，請參閱[Lync Server 2013 的用戶端比較表](lync-server-2013-desktop-client-comparison-tables.md)，以及商務用 skype online 用戶端在[商務用 skype online](http://go.microsoft.com/fwlink/p/?linkid=281902)的用戶端比較表。

<div>

## <a name="integration-with-exchange-server"></a>與 Exchange Server 整合

下表列出整合至 Microsoft Exchange Server 時，混合式部署中支援的功能。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Exchange 內部部署</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 內部部署</strong></p></td>
<td><ul>
<li><p>Outlook 中的 IM/目前狀態</p>
<p>如需詳細資訊，請參閱<a href="lync-server-2013-im-and-presence.md">Lync Server 2013 中的 IM 和目前狀態</a></p></li>
<li><p>透過 Outlook 排程及加入線上會議</p>
<p>如需詳細資訊，請參閱<a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">整合 Microsoft Lync server 2013 與 Microsoft Exchange Server 2013</a></p></li>
<li><p>Outlook Web App 中的 IM/目前狀態</p>
<p>如需詳細資訊，請參閱<a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">在跨部署環境中設定 Microsoft Lync Server 2013</a></p></li>
<li><p>透過 Outlook Web App 排程及加入線上會議</p></li>
<li><p>行動用戶端中的 IM/目前狀態</p></li>
<li><p>在行動用戶端中加入線上會議</p>
<p>如需詳細資訊，請參閱<a href="lync-server-2013-deploying-mobility.md">在 Lync Server 2013 中部署行動</a></p></li>
<li><p>根據 Outlook 行事曆空閒/忙碌資訊發佈狀態</p></li>
<li><p>連絡人清單（透過整合連絡人存放區）</p>
<p>如需詳細資訊，請參閱設定<a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Microsoft Lync Server 2013 以使用整合連絡人存放區</a></p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。<BR>Lync 2013 桌面用戶端是必要的。


</div></li>
<li><p>Lync 2013 用戶端和 Lync Web App 中的高解析度連絡人相片。</p>
<p>如需詳細資訊，請參閱<a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">在 Microsoft Lync Server 2013 中設定高解析度相片的使用</a></p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。


</div></li>
<li><p>會議委派</p>
<p>只有當兩個使用者都在同一個目錄林中進行線上，或者兩者都在內部部署時，才受支援。</p></li>
<li><p>未接的交談記錄和通話記錄會寫入使用者的 exchange 信箱</p></li>
<li><p>在 Exchange 中封存內容（IM 與會議）</p>
<p>如需詳細資訊，請參閱<a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中的存檔部署檢查清單</a></p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。


</div></li>
<li><p>搜尋封存的內容</p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。


</div></li>
<li><p>語音信箱</p>
<p>如需詳細資訊，請參閱<a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">部署內部部署 EXCHANGE UM 以提供 Lync Server 2013 語音信箱</a></p></li>
</ul></td>
<td><ul>
<li><p>Outlook 中的 IM/目前狀態</p>
<p>如需詳細資訊，請參閱設定<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">與 Exchange Online 整合的內部部署 Lync Server 2013</a></p></li>
<li><p>透過 Outlook 排程及加入線上會議</p></li>
<li><p>OWA 中的 IM/目前狀態</p>
<p>如需詳細資訊，請參閱設定<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">與 Exchange Online 整合的內部部署 Lync Server 2013</a></p></li>
<li><p>從 Outlook Web App 排程及加入線上會議</p>
<p>如需詳細資訊，請參閱設定<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">與 Exchange Online 整合的內部部署 Lync Server 2013</a></p></li>
<li><p>行動用戶端中的 IM/目前狀態</p></li>
<li><p>在行動用戶端中加入線上會議</p></li>
<li><p>根據 Outlook 行事曆空閒/忙碌資訊發佈狀態</p></li>
<li><p>連絡人清單（透過 [整合連絡人存放區]）。 如需詳細資訊，請參閱設定<a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Microsoft Lync Server 2013 以使用整合連絡人存放區</a></p>
<div>

> [!NOTE]  
> 僅限 Lync Server 2013。 Lync 2013 桌面用戶端是必要的。


</div></li>
<li><p>Lync 2013 用戶端和 Lync Web App 中的高解析度連絡人相片。</p>
<p>如需詳細資訊，請參閱<a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">在 Microsoft Lync Server 2013 中設定高解析度相片的使用</a>。</p></li>
<li><p>會議委派</p>
<p>只有當兩個使用者都在同一個目錄林中進行線上，或者兩者都在內部部署時，才受支援。</p></li>
<li><p>未接的交談記錄和通話記錄會寫入使用者的 exchange 信箱</p></li>
<li><p>在 Exchange 中封存內容（IM 和會議）。</p>
<p>如需詳細資訊，請參閱<a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中的存檔部署檢查清單</a></p></li>
<li><p>搜尋封存的內容。 如需詳細資訊，請參閱<a href="http://go.microsoft.com/fwlink/p/?linkid=285448">設定 SharePoint EDiscovery 中心的 Exchange</a></p></li>
<li><p>語音信箱。 如需詳細資訊，請參閱<a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">提供 Lync Server 2013 使用者在託管 EXCHANGE UM 上的語音信箱</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Outlook 中的 IM 和目前狀態</p></li>
<li><p>透過 Outlook 排程及加入線上會議</p></li>
<li><p>行動用戶端中的 IM/目前狀態</p></li>
<li><p>未接的交談記錄和通話記錄會寫入使用者的 exchange 信箱</p></li>
<li><p>Lync 2013 用戶端中的高解析度連絡人相片。</p>
<div>

> [!NOTE]  
> 需要 Microsoft Exchange Server 2013。 當使用者駐留在商務用 Skype Online 上時，Lync Web App 不支援此功能。


</div></li>
<li><p>在行動用戶端中加入線上會議</p></li>
<li><p>根據 Outlook 行事曆空閒/忙碌資訊發佈狀態</p></li>
<li><p>會議委派</p>
<p>只有當兩個使用者都在同一個目錄林中進行線上，或者兩者都在內部部署時，才受支援。</p></li>
</ul></td>
<td><ul>
<li><p>Outlook 中的 IM/目前狀態</p></li>
<li><p>透過 Outlook 排程及加入線上會議</p></li>
<li><p>Outlook Web App 中的 IM/目前狀態</p></li>
<li><p>從 Outlook Web App 排程及加入線上會議</p></li>
<li><p>行動用戶端中的 IM/目前狀態</p></li>
<li><p>在行動用戶端中加入線上會議</p></li>
<li><p>根據 Outlook 行事曆空閒/忙碌資訊發佈狀態</p></li>
<li><p>未接的交談記錄和通話記錄會寫入使用者的 exchange 信箱</p></li>
<li><p>連絡人清單（透過整合連絡人存放區）</p>
<div>

> [!NOTE]  
> 需要 Lync Server 2013 用戶端


</div></li>
<li><p>Lync 2013 用戶端和 Lync Web App 中的高解析度連絡人相片</p></li>
<li><p>會議委派</p>
<p>只有當兩個使用者都在同一個目錄林中進行線上，或者兩者都在內部部署時，才受支援。</p></li>
<li><p>在 Exchange 中封存內容（IM 與會議）</p></li>
<li><p>搜尋封存的內容</p></li>
<li><p>語音信箱</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>與 SharePoint 整合

下表列出在與 SharePoint 整合時，Lync Server 2013 混合式部署中支援的功能。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>SharePoint 內部部署</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 內部部署</strong></p></td>
<td><ul>
<li><p>技能搜尋</p></li>
<li><p>SharePoint 中的目前狀態</p></li>
</ul></td>
<td><ul>
<li><p>SharePoint 中的目前狀態</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>SharePoint 中的目前狀態</p></li>
</ul></td>
<td><ul>
<li><p>SharePoint 中的目前狀態</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

