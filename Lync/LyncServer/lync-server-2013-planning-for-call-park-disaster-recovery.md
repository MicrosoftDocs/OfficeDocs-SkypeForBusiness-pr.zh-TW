---
title: Lync Server 2013：規劃通話駐留災難修復
description: Lync Server 2013：規劃通話駐留災難修復。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1d05503f1d8c30f4dd4446a995442d5e2500dbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554279"
---
# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中規劃通話駐留災難修復

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-30_

本節說明一些為災難修復準備通話駐留應用程式的方法，以及有關嚴重損壞修復程式的一些考慮。

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>準備通話駐留災難修復

在準備及執行嚴重損壞復原程式時，請牢記下列幾點。

  - 在進行容量規劃時，請規劃災害復原。 針對嚴重損壞修復容量，成對集區中的每個集區都應該可以處理兩個集區中通話駐留服務的工作量。 如需通話駐留容量規劃的詳細資訊，請參閱 [Lync Server 2013 中的「通話駐留」的容量規劃](lync-server-2013-capacity-planning-for-call-park.md)。

  - 在嚴重損壞復原期間，已被重新導向至備份組區的使用者，在容錯移轉過程中，會使用在備份組區中執行的通話駐留服務。 因此，在嚴重損壞修復時支援通話駐留應用程式，需要在主要集區和備份組區中部署及啟用通話駐留應用程式。

  - 每個集區都必須有有效的軌道編號範圍，以供位於該集區中的使用者用來進行停車電話。

  - 永遠保留為通話駐留上傳的任何自訂音樂保留的個別備份副本。 當您上傳至集區的檔案損毀、損毀或清除時，不會將這些檔案備份成 Lync Server 2013 災難復原程式的一部分，而且將會遺失。

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>通話駐留災害復原考慮

您只能為每個集區定義一組通話駐留應用程式設定設定及一個自訂的音樂暫止音訊檔。 這些設定包括超時閾值、等候音樂、來電收取次數上限及超時 URI。 若要查看這些設定設定，請執行 **CsCpsConfiguration** Cmdlet。 如需 **CsCpsConfiguration** Cmdlet 的詳細資訊，請參閱 [CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)。

在發生嚴重損壞修復時，通話駐留會使用備份組區中的通話駐留應用程式，因此不會備份主要集區中的設定。 如果無法復原主集區，而您部署新集區以取代主要集區，主要集區中的設定會遺失，您必須在新集區中重新設定通話駐留設定和任何自訂的待等候音訊檔案。

如果您使用不同的完整功能變數名稱來部署新集區 (FQDN) 取代主要集區，您必須將與主要集區相關聯的所有通話駐留軌道範圍重新指派給新集區的 FQDN。 若要將軌道範圍重新指派至新集區，您可以使用 Lync Server 控制台或 **get-cscallparkorbit** Cmdlet。 如需 **get-cscallparkorbit** Cmdlet 的詳細資訊，請參閱 [set-get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

