---
title: 部署 Lync Server 2013 用戶端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac6dce30e356ed3161f985f32d8f26dc0e34ac6d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>部署 Lync Server 2013 用戶端

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-19_

您將使用者移轉至 Lync Server 2013 之後，請執行下列動作：

1.  使用新的 Lync Server 2013 伺服器上的用戶端版本篩選器，只允許用戶端登入已安裝最新版更新的。

2.  如有需要，請設定用戶端開機所需的群組原則設定。 如需詳細資訊，請參閱部署文件中的[Lync Server 2013 中的設定用戶端啟動載入原則](lync-server-2013-configuring-client-bootstrapping-policies.md)。 僅當您需要變更現有用戶端的開機原則，或要設定新的用戶端開機原則時，才需要設定這些設定。 若您無意設定用戶端開機原則，或是想要繼續使用舊版的開機原則，便無須採取任何動作。

3.  使用 Lync Server 2013 控制台、 Lync Server 2013 管理命令介面，或兩者，即可設定其他使用者和特定使用者或使用者群組的用戶端原則。 如需詳細資訊，請參閱規劃文件中的[新增和 Lync 2013 的已變更的設定](lync-server-2013-new-and-changed-settings-for-lync-2013.md)。

4.  部署 Lync Server 2013 用戶端，以及最新的累計更新的最新版本。 如需詳細資訊，請參閱部署文件中的[部署用戶端和 Lync Server 2013 中的裝置](lync-server-2013-deploying-clients-and-devices.md)。

5.  （選用）如果貴組織需要 Lync Server 2013 增強型目前狀態隱私權模式時，移轉完成後，會定義用戶端版本原則規則，以防止舊版用戶端登入。 然後，啟用增強型目前狀態隱私權模式。
    
    <div>
    

    > [!IMPORTANT]  
    > 每位使用者或指定的伺服器集區安裝最新版的用戶端版本之前，請勿啟用 Lync 2013 增強顯示狀態隱私權模式。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

