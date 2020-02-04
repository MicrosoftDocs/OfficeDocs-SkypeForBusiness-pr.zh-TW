---
title: Lync Server 2013：設定大型會議的支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e8331c28d5bd06e6a3f7d9dab2fba7db334cd00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>在 Lync Server 2013 中設定大型會議的支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-12_

支援最多1000個使用者的大型會議，需要建立適當的拓撲、會議硬體和軟體先決條件，並適當地設定環境。

<div>

## <a name="topology-requirements"></a>拓撲需求

單一大型會議需要至少一個前端伺服器和一台後端伺服器。 不過，為了提供高可用性，我們建議使用兩個具有鏡像後端伺服器的前端伺服器池。

主持大型會議的使用者必須擁有其使用者帳戶駐留在這個池子中。 不過，我們不建議您在此池中託管其他使用者帳戶。 相反地，只能在大型會議中使用。 最佳做法是在此池中建立特殊的使用者帳戶，只是用來主持大型會議。 因為大型會議設定已針對效能優化，所以將它當作一般使用者使用時，可能會發生問題，例如在涉及 PSTN 端點時無法將 P2P 會話升級至會議。

管理只有兩個前端伺服器的池需要一些特殊的考慮。 如需詳細資訊，請參閱[Lync Server 2013 中前端伺服器、立即訊息和目前狀態的拓撲與元件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。

此外，如果您想要選擇性地針對大型會議所用的池子提供災害復原備份與容錯移轉，您可以將它與其他資料中心的專用池進行配對。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

![大型會議集區組態](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "大型會議集區組態")

關於拓撲的其他注意事項包括：

  - 儲存會議內容需要檔案共用，並在已部署並啟用封存伺服器的情況下，儲存存檔檔案。 檔案共用可以專用於該文件庫，或者可以是部署該池之網站上另一個池所使用的相同檔案共用。 如需有關設定檔案共用的詳細資訊，請參閱[設定 Lync Server 2013 的檔案儲存空間](lync-server-2013-configure-dfs-file-storage.md)。

  - 您必須具備 Office Web Apps 伺服器，才能在大型會議中啟用 PowerPoint 簡報功能。 Office Web Apps 伺服器可以專用於大型會議池，也可以是部署專用池之網站上其他池所使用的 Office Web Apps 伺服器。

  - 前端伺服器的負載平衡需要針對 HTTP 流量進行硬體負載平衡（例如會議內容下載）。 針對 SIP 流量，建議使用 DNS 負載平衡。 如需詳細資訊，請參閱[Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。

  - 如果您想要將監視伺服器用於專用大型會議池，我們建議使用監視伺服器及其在 Lync Server 部署中的所有前端伺服器池中共用的資料庫。

</div>

<div>

## <a name="hardware-and-software-requirements"></a>硬體和軟體需求

在專用大型會議池中，伺服器的硬體需求與其他 Lync Server 2013 伺服器的需求相同。 如需硬體需求的詳細資訊，請參閱「[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)」。

專用大型會議池中的伺服器必須符合所有 Lync Server 2013 軟體需求。 如需軟體需求的詳細資訊，請參閱下列檔：

  - [Lync Server 2013 中的伺服器及工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)

  - [Lync Server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)

此外，Lync Server 2013 和所有 Lync Server 2013 用戶端都必須擁有最新的更新。

</div>

<div>

## <a name="configuration-requirements"></a>配置需求

建議您專門針對大型會議建立新的會議策略，然後將會議原則指派給駐留在專門大型會議池的使用者。 使用下列設定來設定會議原則：

  - 將**MaxMeetingSize**選項設定為**1000**。 （預設值為**250**）。

  - 將**AllowLargeMeetings**選項設定為**True**。

  - 將 [ **EnableAppDesktopSharing** ] 選項設定為 [**無**]。

  - 將 [ **AllowUserToScheduleMeetingsWithAppSharing** ] 選項設定為 [ **False**]。

  - 將 [ **AllowSharedNotes** ] 選項設定為 [ **False**]。

  - 將 [ **AllowAnnotations** ] 選項設定為 [ **False**]。

  - 將**DisablePowerPointAnnotations**選項設定為**True**。

  - 將 [ **AllowMultiview** ] 選項設定為 [ **False**]。

  - 將 [ **EnableMultiviewJoin** ] 選項設定為 [ **False**]。

<div>


> [!NOTE]  
> Lync Server 2013 中的1000使用者大型會議支援要求會議排程的會議原則中的 [ <STRONG>AllowLargeMeetings</STRONG> ] 設定設為 true。 當此設定設為 true 時，當使用者加入此類會議時，Lync 體驗會針對額外的大型會議進行優化。 特別是在大型會議中，Lync 不會顯示完整會議參與者清單的初始或更新，這是用戶端和 Lync Server 2013 的效能瓶頸。 [Lync] 只會顯示使用者與會議簡報者清單的相關資訊。 Lync 仍會正確顯示大型會議中可用的參與者總數。



</div>

除了 [**最大會議大小**] 設定之外，您還需要在此處指定的所有其他會議原則設定，才能停用大型會議中不需要的會議功能。

此外，您還需要設定專用的大型會議池，讓駐留在該池的每個 Lync Server 2013 使用者，並負責管理會議排程，擁有適當的許可權。 若要這樣做，請執行下列動作：

  - 將 [**指定為簡報者**] 選項設定為 [**無**]。 通常，大型會議所有參與者的一或多個使用者都是簡報者，所以不應以簡報者的身分自動准許參與者參加大型會議。 相反地，簡報者應該在會議排程時間明確指定，或在大型會議中明確地進行升級。

  - 請確認未選取 [**預設為指派的會議類型**] 核取方塊。 此設定可控制 Lync 2013 的線上會議增益集是否總是使用召集人指派的會議來排程會議，這表示排程的會議有相同的聯接 URL 和音訊資訊。 在小型群組共同作業案例中，由於每個人都有自己指派的會議，且常數加入 URL 和音訊資訊都能協助您更快速地加入會議，因此在小組共同作業案例中擁有此類會議。 不過，在大型會議案例中，大型會議支援人員會使用一組使用者認證來安排大型會議，然後提供加入 Url 和音訊資訊給會議申請者。 在這種情況下，使用不同的 URL 加入每個會議都能更好。

  - 除非必要，否則請確認未選取 [**以預設方式承認匿名使用者**] 核取方塊。 此設定會影響在未使用指派的會議時，由 Lync 2013 的線上會議增益集排程的預設會議存取類型。 此設定的適當選項視貴組織的需求而定。 如果貴組織的大多數大型會議都是內部會議，請勿選取此選項。 如果大多數大型會議都需要外部使用者能夠加入，請選取此選項。

</div>

</div>

<span> </span>

</div>

</div>

</div>

