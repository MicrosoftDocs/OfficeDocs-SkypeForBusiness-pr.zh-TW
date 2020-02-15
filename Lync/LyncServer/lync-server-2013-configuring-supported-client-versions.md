---
title: Lync Server 2013： 設定支援的用戶端版本
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 326a428003a7836adef588942765909b753124ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>在 Lync Server 2013 中設定支援的用戶端版本

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-12-14_

在 Lync Server 2013 中，您可以設定來指定您的環境中支援的用戶端版本的用戶端版本原則。 此外，您可以使用全域的用戶端版本設定來指定預設巨集指令還沒有版本的用戶端原則定義，因此，都沒有明確支援或限制。

您也可以使用用戶端版本原則來管理用戶端更新。 當您設定用戶端版本原則，並使用 **[允許並升級**] 與 [**封鎖並升級**選項時，用戶端會收到更新的軟體，從 Windows Server 更新服務 （如果您正在使用這項服務） 或 Microsoft Update。

<div>

## <a name="client-version-policy-settings"></a>用戶端版本原則設定

預設用戶端版本原則需要所有用戶端執行 Lync。 如果您的環境中的用戶端執行舊版 Communicator，您可能需要重新設定用戶端版本規則，以避免用戶端和裝置的意外封鎖或更新連線至 Lync Server 2013 時。 您可以修改預設規則，或者您可以在用戶端版本原則清單中，若要覆寫預設規則新增較高的規則。 此外，當發行累積更新 (Cu)，您應該設定為需要最新的更新用戶端版本原則。 如需詳細資訊，請參閱作業文件中的[指定，可以用來登入 Lync Server 2013 的用戶端應用程式](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

