---
title: Lync Server 2013：設定大型會議的支援
description: Lync Server 2013：設定大型會議的支援。
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
ms.openlocfilehash: cb04b4192c6daa9e6ea255b52566dacee1bd2dcd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554209"
---
# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>在 Lync Server 2013 中設定大型會議的支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-12_

支援最多1000使用者的大型會議，需要建立適當的拓撲、會議硬體和軟體必要條件，並適當地設定環境。

<div>

## <a name="topology-requirements"></a>拓撲需求

單一大型會議需要至少一部前端伺服器和一部後端伺服器。 不過，為了提供高可用性，我們建議使用兩部前端伺服器集區和鏡像後端伺服器。

主控大型會議的使用者必須擁有位於此集區中的使用者帳戶。 不過，我們不建議您在此集區中主控其他使用者帳戶。 而只是用於大型會議。 最佳作法是在此集區中建立特殊的使用者帳戶，僅供主控大型會議使用。 因為大型會議設定已經針對效能進行優化，所以以一般使用者的身分使用它時，可能會發生問題，例如，當涉及 PSTN 端點時，無法將 P2P 會話提升為會議。

若要管理恰好兩部前端伺服器的集區，需要一些特殊的考慮。 如需詳細資訊，請參閱 [Lync Server 2013 中的前端伺服器、立即訊息及顯示狀態的拓撲和元件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。

此外，如果您想要選擇性地為大型會議所用的集區提供嚴重損壞修復備份和容錯移轉，您可以將它與不同資料中心的專用集區配對。 如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

![大型會議集區設定](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "大型會議集區設定")

拓撲的其他注意事項包括：

  - 需要有檔案共用，才能儲存會議內容，以及在部署及啟用封存伺服器時儲存封存檔。 檔案共用可以專用於集區，也可以是部署集區之網站上其他集區所使用的相同檔案共用。 如需設定檔案共用的詳細資訊，請參閱 [Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)。

  - 若要在大型會議中啟用 PowerPoint 簡報功能，必須使用 Office Web Apps Server。 Office Web Apps Server 可以專用於大型會議集區，也可以是部署專用集區之網站上其他集區所使用的 Office Web Apps Server。

  - 前端伺服器的負載平衡需要對 HTTP 流量 (例如「會議內容下載) 」的硬體負載平衡。 建議使用 DNS 負載平衡進行 SIP 流量。 如需詳細資訊，請參閱 [Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。

  - 如果您想要對專用大型會議集區使用監控伺服器，我們建議您使用在 Lync Server 部署中所有前端伺服器集區中共用的監控伺服器及其資料庫。

</div>

<div>

## <a name="hardware-and-software-requirements"></a>軟硬體需求

專用大型會議集區中之伺服器的硬體需求與其他 Lync Server 2013 伺服器的硬體需求相同。 如需硬體需求的詳細資訊，請參閱「[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)」。

專用大型會議集區中的伺服器必須符合所有的 Lync Server 2013 軟體需求。 如需軟體需求的詳細資訊，請參閱下列檔：

  - [Lync Server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)

  - [Lync Server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)

此外，Lync Server 2013 和所有 Lync Server 2013 用戶端都必須具有最新的更新。

</div>

<div>

## <a name="configuration-requirements"></a>設定需求

建議您專門為大型會議建立新的會議原則，然後將會議原則指派給位於專屬大型會議集區的使用者。 使用下列設定來設定會議原則：

  - 將 **MaxMeetingSize** 選項設定為 **1000**。  (預設值為 **250**。 ) 

  - 將 **AllowLargeMeetings** 選項設定為 **True**。

  - 將 **EnableAppDesktopSharing** 選項設定為 [ **無**]。

  - 將 **AllowUserToScheduleMeetingsWithAppSharing** 選項設定為 **False**。

  - 將 **AllowSharedNotes** 選項設定為 **False**。

  - 將 **AllowAnnotations** 選項設定為 **False**。

  - 將 **DisablePowerPointAnnotations** 選項設定為 **True**。

  - 將 **AllowMultiview** 選項設定為 **False**。

  - 將 **EnableMultiviewJoin** 選項設定為 **False**。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中對1000使用者大型會議的支援，需要將會議排程器的會議原則中的 [ <STRONG>AllowLargeMeetings</STRONG> ] 設定設為 true。 當此設定設為 true 時，當使用者加入這類會議時，Lync 體驗會針對額外的大型會議進行優化。 特別是在大型會議中，Lync 不會顯示完整會議參與者清單的初始或更新，也就是用戶端和 Lync Server 2013 的性能瓶頸。 相反地，Lync 只會顯示使用者的相關資訊和會議的簡報者清單。 Lync 仍會正確顯示大型會議中可用的參與者總數。



</div>

除了 [ **最大會議大小** ] 設定之外，您還需要在這裡指定的所有其他會議原則設定，才能停用大型會議中不需要的會議功能。

此外，您必須設定專門的大型會議集區，使位於集區中的每個 Lync Server 2013 使用者都擁有適當的許可權。 若要這麼做，請執行下列操作：

  - 將 [ **指定為簡報者** ] 選項設定為 [ **無**]。 通常，一或多個大型會議參與者的使用者都是簡報者，所以不應該以簡報者的身分，將參與者自動承認為大型會議。 相反地，簡報者應明確指派會議排程時間，或是在大型會議期間明確升級。

  - 請確定未選取 [ **依預設指派指派會議類型** ] 核取方塊。 此設定可控制 Lync 2013 的線上會議增益集是否一定要使用召集人指派的會議來排程會議，這表示已排程的會議具有相同的加入 URL 和音訊資訊。 在小型群組共同作業案例中，有這種指派的會議類型可順利運作，因為每個人都有自己的指派會議，而常數加入 URL 和音訊資訊可協助協助加入更快速的會議。 不過，在大型會議案例中，大型會議支援人員會使用一組使用者認證來安排大型會議，然後為會議申請者提供加入 URLs 和音訊資訊。 在此情況下，使用不同的 URL 來加入每個會議可更好地運作。

  - 除非有必要，否則請確定未選取 [ **預設會承認匿名使用者** ] 核取方塊。 在未使用指派的會議時，此設定會影響 Lync 2013 之線上會議增益集排程的預設會議存取類型。 此設定的適當選項取決於組織的需求。 如果貴組織大多數的大型會議為內部會議，請勿選取此選項。 如果大多數大型會議都要求外部使用者可以加入，請選取此選項。

</div>

</div>

<span> </span>

</div>

</div>

</div>

