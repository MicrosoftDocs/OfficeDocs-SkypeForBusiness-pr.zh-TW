---
title: 'Lync Server 2013: Overview of 群組來電接聽'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 222d587f7c4972a8aee313d3d66da578cde08960
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a>群組來電接聽 Lync Server 2013 中的概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-12_

群組呼叫收取，Cumulative Updates for Lync Server 2013 中的新功能： 2 月 2013年可讓使用者接聽來電從他們自己的電話其同事。 這項新功能會增加使用者的一行的可用性讓其他使用者可以撥出通話收取群組號碼接聽來電。 部署群組來電接聽時，會路由傳送至語音信箱的來電數目可以大幅降低，也就是特別適合用來從組織外部的客戶的通話。

群組來電接聽功能特別設計來開啟 office 環境中的業務單位。 傳入呼叫並不中斷，因為他們撥打只會在預定目的地。 聽到鈴聲，其他使用者不過，可以仍收取通話只要撥號群組編號。

在環境中，使用者不是所位於中開啟 office 版面配置或地理位置分散共用共同責任的使用者，小組通話會呈現最適合的解決方案。 群組來電接聽與小組通話的主要差異是，與群組來電接聽來電鈴響只會在預定的目的地，但任何人仍然可以選擇接聽撥出群組號碼。 與小組通話通話響起所有小組成員的電話，但小組中的任何使用者可以接聽電話時接電話。 群組來電接聽與小組通話其他差異是群組來電接聽由系統管理員，透過 Lync Server 管理。 與小組通話，使用者會使用 Lync 用戶端管理該功能。 使用群組來電接聽，因此，這方面的通話管理可以是集中式。

群組來電接聽做為基礎的通話駐留應用程式。 當您部署群組來電接聽時，您可以設定通話駐留軌道表各種不同的範圍內的指定為呼叫收取群組號碼的分機號碼。 例如通話駐留軌道數字、 呼叫收取群組號碼必須不有任何使用者或電話指派給他們的虛擬分機。 您將部署群組來電接聽每個前端集區可以有一或多個範圍的通話收取群組數字。 在 Lync Server 部署，群組號碼範圍必須是全域唯一的。

<div>


> [!NOTE]  
> 會指定為 [群組來電接聽通話駐留軌道表中的數字無法管理或檢視使用 Lync Server Control Panel 的號碼範圍。 若要查看在通話駐留軌道表中的所有號碼範圍的唯一方法是使用 Lync Server 管理命令介面。 同樣地，若要新增，唯有修改或移除群組來電接聽數字是使用 Lync Server 管理命令介面。



</div>

設定通話收取群組號碼之後，您會將使用者指派給通話收取群組中。 指派給呼叫收取群組的任何使用者可以有其其他使用者所接聽的通話。 當接獲指派給呼叫收取群組的使用者時，通知來電者的其他使用者可以接聽它來手動撥打的通話收取群組編號。 挑選通話之使用者不必是群組的成員。 當呼叫收取的另一位使用者時，就會傳送通知，原本呼叫的數字。

<div>


> [!NOTE]  
> 使用者可以是只有一個呼叫收取群組的成員。



</div>

<div>


> [!NOTE]  
> 雖然 Lync Server 部署中的任何使用者可以接聽通話收取群組成員的呼叫，接聽電話的人必須知道正確的呼叫收取群組號碼。



</div>

如果使用者撥打通話收取群組數字，以接聽來電，當群組中的多個電話響鈴時，使用者會接聽來電，具有最長響鈴。

同時響鈴設定適用於擁有群組呼叫收取] 目錄的使用者。 也就是撥至具有群組來電接聽的使用者將會撥打的所有設定的目的地，與另一位使用者可以接聽來電。 此規則的例外是當使用者設定同時響鈴呼叫所有小組成員。

群組來電接聽無法用來接聽來電下列幾種：

  - 私人線路的電話

  - 呼叫從連絡人朋友和家人獲指派私人關係
    
    <div>
    

    > [!TIP]  
    > 呼叫收取群組成員的使用者可能會使某些藉由將連絡人標示為已在 Lync 用戶端的個人連絡人正在擷取透過群組來電接聽的來電。 若要將標示為個人連絡人的連絡人，將連絡人的私人關係設朋友和家人。 從 [連絡人] 私人關係與任何傳入呼叫設朋友並無法使用群組來電接聽擷取系列。

    
    </div>

  - 視訊部分的音訊/視訊通話
    
    <div>
    

    > [!NOTE]  
    > 如果使用者接聽，音訊/視訊通話，使用者會收到僅音訊。 呼叫的人員或接聽電話的人員可以擴大以加入視訊通話。

    
    </div>

  - 同時響鈴的通話，路由傳送到小組呼叫成員

  - 通話路由傳送至代理人

  - 通話路由傳送至回應群組

下列類型的使用者無法參與群組來電接聽。 也就是說，不應該包含群組來電接聽群組中，和他們無法揀選使用者已啟用的群組來電接聽通話。

  - 位於 online 混合式部署中的使用者

  - 不位於 Cumulative Updates for Lync Server 2013 與 Lync Server 2013 集區的使用者： 在內部部署中的年 2 月 2013年

如果沒有人的用戶端設定中指定為路由傳送通話收取群組成員，呼叫藉由呼叫的答案。 也就是在呼叫移至語音信箱或郵件會轉送到不同的目的，用戶端設定中所指定。

</div>

<span> </span>

</div>

</div>

</div>

