---
title: Lync Server 2013：支援的混合式設定
description: Lync Server 2013：支援的混合式設定。
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
ms.openlocfilehash: 1a51667a9c10322b4e2503d81c8b3ddb07c17855
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550879"
---
# <a name="supported-lync-server-2013-hybrid-configurations"></a>支援的 Lync Server 2013 混合式設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-05-10_

您可以設定 Lync Server 2013 部署，以與 Microsoft Exchange Server 2010 和 Microsoft Exchange Server 2013，以及內部部署和線上的 SharePoint 伺服器整合。 除非另有指定，否則下表中所列的功能會支援所有用戶端。 如需用戶端支援的詳細資訊，請參閱用戶端上的 [Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) 和商務用 skype online 用戶端比較表（ [適用于商務用 skype online](https://go.microsoft.com/fwlink/p/?linkid=281902)）。

<div>

## <a name="integration-with-exchange-server"></a>與 Exchange Server 整合

下表列出與 Microsoft Exchange Server 整合時，混合式部署支援的功能。


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
<p>如需詳細資訊，請參閱 <a href="lync-server-2013-im-and-presence.md">Lync Server 2013 中的 IM 和目前狀態</a></p></li>
<li><p>透過 Outlook 排程及加入線上會議</p>
<p>如需詳細資訊，請參閱 <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">整合 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013</a></p></li>
<li><p>Outlook Web App 中的 IM/目前狀態</p>
<p>如需詳細資訊，請參閱 <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">在跨部署環境中設定 Microsoft Lync Server 2013</a></p></li>
<li><p>透過 Outlook Web App 排程及加入線上會議</p></li>
<li><p>行動用戶端中的 IM/目前狀態</p></li>
<li><p>在行動用戶端加入線上會議</p>
<p>如需詳細資訊，請參閱 <a href="lync-server-2013-deploying-mobility.md">在 Lync Server 2013 部署行動性</a></p></li>
<li><p>根據 Outlook 行事曆空閒/忙碌資訊的發行狀態</p></li>
<li><p>透過整合連絡人存放區 (的連絡人清單) </p>
<p>如需詳細資訊，請參閱設定 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Microsoft Lync Server 2013 以使用整合連絡人存放區</a></p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。<BR>需要 Lync 2013 桌面用戶端。


</div></li>
<li><p>Lync 2013 用戶端和 Lync Web App 中的高解析度連絡人相片。</p>
<p>如需詳細資訊，請參閱 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">在 Microsoft Lync Server 2013 中設定高解析度相片的使用</a></p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。


</div></li>
<li><p>會議委派</p>
<p>只有在兩位使用者都位於相同樹系中的線上，或兩者都位於內部部署時，才受支援。</p></li>
<li><p>錯過的交談記錄及通話記錄會寫入使用者的 exchange 信箱</p></li>
<li><p>在 Exchange 中封存內容 (IM 和會議) </p>
<p>如需詳細資訊，請參閱 <a href="lync-server-2013-deployment-checklist-for-archiving.md">在 Lync Server 2013 中封存的部署檢查清單</a></p>
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
<p>如需詳細資訊，請參閱 <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">部署內部部署 EXCHANGE UM 以提供 Lync Server 2013 語音信箱</a></p></li>
</ul></td>
<td><ul>
<li><p>Outlook 中的 IM/目前狀態</p>
<p>如需詳細資訊，請參閱設定 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">內部部署 Lync Server 2013 與 Exchange Online 整合</a></p></li>
<li><p>透過 Outlook 排程及加入線上會議</p></li>
<li><p>OWA 中的 IM/顯示狀態</p>
<p>如需詳細資訊，請參閱設定 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">內部部署 Lync Server 2013 與 Exchange Online 整合</a></p></li>
<li><p>從 Outlook Web App 排程及加入線上會議</p>
<p>如需詳細資訊，請參閱設定 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">內部部署 Lync Server 2013 與 Exchange Online 整合</a></p></li>
<li><p>行動用戶端中的 IM/目前狀態</p></li>
<li><p>在行動用戶端加入線上會議</p></li>
<li><p>根據 Outlook 行事曆空閒/忙碌資訊的發行狀態</p></li>
<li><p>透過整合連絡人存放區)  (的連絡人清單。 如需詳細資訊，請參閱設定 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Microsoft Lync Server 2013 以使用整合連絡人存放區</a></p>
<div>

> [!NOTE]  
> 僅限 Lync Server 2013。 需要 Lync 2013 桌面用戶端。


</div></li>
<li><p>Lync 2013 用戶端和 Lync Web App 中的高解析度連絡人相片。</p>
<p>如需詳細資訊，請參閱 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">在 Microsoft Lync Server 2013 中設定高解析度相片的使用</a>。</p></li>
<li><p>會議委派</p>
<p>只有在兩位使用者都位於相同樹系中的線上，或兩者都位於內部部署時，才受支援。</p></li>
<li><p>錯過的交談記錄及通話記錄會寫入使用者的 exchange 信箱</p></li>
<li><p>在 Exchange 中封存內容 (IM 和會議) 。</p>
<p>如需詳細資訊，請參閱 <a href="lync-server-2013-deployment-checklist-for-archiving.md">在 Lync Server 2013 中封存的部署檢查清單</a></p></li>
<li><p>搜尋封存的內容。 如需詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">Configure Exchange for SharePoint EDiscovery Center</a></p></li>
<li><p>語音信箱。 如需詳細資訊，請參閱 <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">在主控 EXCHANGE UM 上提供 Lync Server 2013 使用者語音信箱</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Outlook 中的 IM 和目前狀態</p></li>
<li><p>透過 Outlook 排程及加入線上會議</p></li>
<li><p>行動用戶端中的 IM/目前狀態</p></li>
<li><p>錯過的交談記錄及通話記錄會寫入使用者的 exchange 信箱</p></li>
<li><p>Lync 2013 用戶端中的高解析度連絡人相片。</p>
<div>

> [!NOTE]  
> 需要 Microsoft Exchange Server 2013。 當使用者位於商務用 Skype Online 時，Lync Web App 不支援此功能。


</div></li>
<li><p>在行動用戶端加入線上會議</p></li>
<li><p>根據 Outlook 行事曆空閒/忙碌資訊的發行狀態</p></li>
<li><p>會議委派</p>
<p>只有在兩位使用者都位於相同樹系中的線上，或兩者都位於內部部署時，才受支援。</p></li>
</ul></td>
<td><ul>
<li><p>Outlook 中的 IM/目前狀態</p></li>
<li><p>透過 Outlook 排程及加入線上會議</p></li>
<li><p>Outlook Web App 中的 IM/目前狀態</p></li>
<li><p>從 Outlook Web App 排程及加入線上會議</p></li>
<li><p>行動用戶端中的 IM/目前狀態</p></li>
<li><p>在行動用戶端加入線上會議</p></li>
<li><p>根據 Outlook 行事曆空閒/忙碌資訊的發行狀態</p></li>
<li><p>錯過的交談記錄及通話記錄會寫入使用者的 exchange 信箱</p></li>
<li><p>透過整合連絡人存放區 (的連絡人清單) </p>
<div>

> [!NOTE]  
> 需要 Lync Server 2013 用戶端


</div></li>
<li><p>Lync 2013 用戶端和 Lync Web App 中的高解析度連絡人相片</p></li>
<li><p>會議委派</p>
<p>只有在兩位使用者都位於相同樹系中的線上，或兩者都位於內部部署時，才受支援。</p></li>
<li><p>在 Exchange 中封存內容 (IM 和會議) </p></li>
<li><p>搜尋封存的內容</p></li>
<li><p>語音信箱</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>與 SharePoint 整合

下表列出 Lync Server 2013 混合部署與 SharePoint 整合時支援的功能。


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
<li><p>目前狀態 SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>目前狀態 SharePoint</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>目前狀態 SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>目前狀態 SharePoint</p></li>
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

