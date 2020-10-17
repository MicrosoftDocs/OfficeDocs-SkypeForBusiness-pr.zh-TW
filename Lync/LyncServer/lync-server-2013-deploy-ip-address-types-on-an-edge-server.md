---
title: Lync Server 2013：在 Edge Server 上部署 IP 位址類型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210819547a78905865ebe2dca09d03ab597f33af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531420"
---
# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a>在 Lync Server 2013 的 Edge Server 上部署 IP 位址類型

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-14_

使用拓撲產生器，執行下列程式中的步驟，以在 Edge Server 上部署 IP 位址類型。

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a>部署 Edge Server 上的 IP 位址類型

1.  在 [拓撲產生器] 的 [ **Edge**集區] 底下，于集區中的伺服器上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。  (或者，選取伺服器，然後按一下 [**動作**] 功能表中的 [**編輯屬性**]。 ) 

2.  在 **[編輯內容]** 視窗中，選取您要支援的 IP 位址設定。下列圖例展示內部介面與外部介面的雙重堆疊設定。
    
    **雙重堆疊的 Edge Server 內部介面**
    
    ![Lync Server 一般屬性頁面](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server 一般屬性頁面")
    
    **雙重堆疊的 Edge Server 外部介面**
    
    ![Lync Server 下一個躍點/外部設定頁面](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server 下一個躍點/外部設定頁面")

3.  您必須針對所選取的每個位址類型提供適當的內部及外部位址。

</div>

</div>

<span> </span>

</div>

</div>

</div>

