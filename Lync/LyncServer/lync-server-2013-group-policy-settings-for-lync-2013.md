---
title: Lync Server 2013： Lync 2013 的群組原則設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72493338d854cc0aff63fde5eabb5d7a281fd50e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500710"
---
# <a name="group-policy-settings-for-lync-2013"></a>Lync 2013 的群組原則設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

在舊版的 Lync 和 Office Communicator 中，有一個獨立的 Communicator 系統管理範本可用於設定用戶端群組原則設定。 對於 Lync 2013，新的系統管理範本檔案 ( admx 和 adml 檔案) 隨附于 Office 群組原則系統管理範本。 Lync 2013 admx 和 adml 檔案的可用性可讓您下載範本，以及集中管理所有 Office 程式和語言套件的群組原則設定。 如需詳細資訊，請參閱 Office 2013 檔中的「Office 2013 系統管理範本檔案 (ADMX，ADML) 」 <https://go.microsoft.com/fwlink/p/?linkid=267516> 。

<div>

## <a name="client-bootstrapping-policies"></a>用戶端啟動原則

有幾個用戶端啟動原則是您必須在使用者第一次登入伺服器之前設定的。 因為在用戶端登入並開始從伺服器接收頻內佈建設定之前，這些原則就已生效，所以您可以使用 [群組原則] 來設定它們。 如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定用戶端引導原則](lync-server-2013-configuring-client-bootstrapping-policies.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

