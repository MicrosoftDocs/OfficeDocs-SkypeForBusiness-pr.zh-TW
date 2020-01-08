---
title: Lync Server 2013：大型會議支援常見問題
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c8355374a773afe3d6da22c886a2b103b13abd3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>大型會議支援 Lync Server 2013 的常見問題

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

下列各節提供建立及執行大型會議的常見問題的解答。

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>問：有多少使用者可以參與大型會議？

Lync Server 使用者模型會指定共用區中的250使用者限制，或是在專用於大型會議的池中的1000使用者，但這些數位只代表我們已測試的使用者數量，而且只代表我們在測試中使用的特定硬體組。 根據我們的測試，我們建議對最大大小的限制。 不過，您可以設定一或多個會議原則（您是使用 Lync Server 管理命令介面中的 Windows PowerShell Cmdlet 設定，或是使用 Lync Server），來控制貴組織中的會議所允許的實際參與者人數[控制台]）。 您在會議原則中指定的數位可以是介於1和4294967295之間的任何32位整數，但建議的大小介於2與250參與者之間（含）。預設值為250。

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>問：我可以在擁有大量會議的池中擁有多少個會議或其他工作負載？

為了確保最多1000參與者的大型會議中的最佳使用者體驗，我們建議您只在專門針對大型會議的池中，一次只託管一個大型會議。 我們也建議您在大型會議進行期間，不允許任何其他工作負荷在該池中執行。

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>問：是否應該將大型會議的召集人託管在專用的池中？

不。 我們建議您不要將專用員工以外的任何使用者集中管理，以在專用的泳池上管理大型會議。 這可防止其他即時通訊流量造成在該池中託管大型會議的問題。 您應該使用大型會議排程員工的使用者帳戶，在專用的泳池上排程大型會議。 您應該將會議召集人的使用者帳戶（要求大型會議的使用者）新增為大型會議的簡報者。

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>問：我可以在大型會議中使用哪些媒體形式？

最多1000個使用者可包含音訊、影片、PowerPoint 共用、白板和目前狀態輪詢等大型會議。

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>問：我可以在大型會議中使用群組立即訊息（IM）嗎？

是。 不過，大量的立即訊息（尤其是當由大量會議參與者傳送時），會因為 IM 視窗中的快速文字滾動問題而影響使用者體驗。 傳送大量立即訊息給1000的使用者也可能會造成大量的伺服器負載，這可能會影響效能。 一般來說，只有問題與解答（Q\&As）才需要 IM。

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>使用者可以從手機撥入來加入大型會議嗎？

是。 如果 Lync Server 2013 池已正確部署且已啟用電話撥入式會議，使用者將能夠撥入來加入大型會議。 我們的測試顯示，最多15% 的1000使用者可以在10分鐘內加入大型會議。

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>問：我可以在虛擬拓朴中主持大型會議嗎？

我們未在虛擬拓撲中測試大型會議，因此我們不支援使用虛擬機器來託管大型會議的專用池。

</div>

</div>

<span> </span>

</div>

</div>

</div>

