---
title: Lync Server 2013：設定電話撥入式會議的撥號對應表
description: Lync Server 2013：設定電話撥入式會議的撥號對應表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28123f905288ce35b6f470168962a3d8e6faa22b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567579"
---
# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中設定電話撥入式會議的撥號對應表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

當您部署電話撥入式會議時，您必須建立或修改一或多個用於路由撥入存取電話號碼的撥號對應表。 請確定每個撥號對應表中至少有一個正規化規則，以 e.164 格式將電話分機號碼轉換成完整的電話號碼。 使用電話撥入式會議加入會議的使用者，將其個人身分識別號碼 (PIN) 和其電話號碼輸入，以供已驗證的企業使用者加入會議。 您需要正規化規則，將分機轉換成完整的電話號碼，讓使用者在輸入電話分機時可驗證。

若要設定電話撥入式會議的撥號對應表，請執行下列操作：

  - 不論您是部署企業語音，請修改全域撥號對應表，以加入電話撥入式會議區域，並確定正規化規則正確地轉換您的撥入存取號碼。 如需詳細指示，請參閱 [在 Lync Server 2013 中修改撥號](lync-server-2013-modify-a-dial-plan.md)對應表。

  - 如果您未部署企業語音，請建立電話撥入式會議存取號碼的撥號對應表。 請務必加入電話撥入式會議區域。 如需詳細指示，請參閱 [Create a 撥號 plan In Lync Server 2013](lync-server-2013-create-a-dial-plan.md)。

  - 如果您部署了企業語音，請視需要修改 Enterprise Voice 撥號對應表，以包含地區，並使用適當的正規化規則來撥打撥入存取號碼。 如需詳細指示，請參閱 [在 Lync Server 2013 中修改撥號](lync-server-2013-modify-a-dial-plan.md)對應表。 您也可以建立專用的撥號對應表，只用于撥入存取號碼。 如需詳細指示，請參閱 [Create a 撥號 plan In Lync Server 2013](lync-server-2013-create-a-dial-plan.md)。

如需規劃地區的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md) 。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中查看撥號對應表資訊](lync-server-2013-view-dial-plan-information.md)

  - [在 Lync Server 2013 中建立撥號對應表](lync-server-2013-create-a-dial-plan.md)

  - [在 Lync Server 2013 中修改撥號對應表](lync-server-2013-modify-a-dial-plan.md)

  - [在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

