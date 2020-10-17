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
ms.openlocfilehash: 9d42b410765b4cf8b7a52221f76ba532347ee3ef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503000"
---
# <a name="deploy-lync-server-2013-clients"></a>部署 Lync Server 2013 用戶端

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

將使用者遷移至 Lync Server 2013 之後，請執行下列操作：

1.  在新的 Lync Server 2013 伺服器上使用用戶端版本篩選器，只允許安裝了最新更新的用戶端登入。

2.  如有需要，請設定用戶端開機所需的群組原則設定。 如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定用戶端引導原則](lync-server-2013-configuring-client-bootstrapping-policies.md) 。 僅當您需要變更現有用戶端的開機原則，或要設定新的用戶端開機原則時，才需要設定這些設定。 若您無意設定用戶端開機原則，或是想要繼續使用舊版的開機原則，便無須採取任何動作。

3.  使用 Lync Server 2013 控制台、Lync Server 2013 管理命令介面或兩者，針對特定使用者或使用者群組設定其他使用者和用戶端原則。 如需詳細資訊，請參閱規劃檔中的 [新的和變更的 Lync 2013 設定](lync-server-2013-new-and-changed-settings-for-lync-2013.md) 。

4.  部署最新版本的 Lync Server 2013 用戶端，以及最新的累計更新。 如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中部署用戶端和裝置](lync-server-2013-deploying-clients-and-devices.md) 。

5.   (選用) 若您的組織需要 Lync Server 2013 增強型目前狀態隱私權模式，遷移完成後，請定義用戶端版本原則規則，以防止舊版用戶端版本登入。 然後，啟用增強型目前狀態隱私權模式。
    
    <div>
    

    > [!IMPORTANT]  
    > 在指定伺服器集區上的每位使用者都已安裝最新的用戶端版本之前，請勿啟用 Lync 2013 增強顯示狀態隱私權模式。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

