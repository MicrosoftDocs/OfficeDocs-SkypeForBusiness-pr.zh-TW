---
title: 新增 Edge Server 內部 IP 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: 使用此頁面指定 Edge Server 的內部 IP 位址和內部完整網域名稱 (FQDN)。
ms.openlocfilehash: 7c4951ec7e2c906ea7913ab8d3942310942c9091f25e5b3d1ecc88d85d93e14a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302567"
---
# <a name="add-edge-server-internal-ip-2010"></a>新增 Edge Server 內部 IP 2010

使用此頁面指定 Edge Server 的內部 IP 位址和內部完整網域名稱 (FQDN)。

您指定的 FQDN 必須與伺服器上設定的電腦名稱相同。 根據預設，未加入網域之電腦的電腦名稱是簡稱，不是 FQDN。 拓撲產生器使用 Fqdn，而非短名稱。 因此，在要部署為 Edge Server 的電腦 (未加入網域) 名稱中，您必須設定網域名稱系統 (DNS) 尾碼。 如需將 DNS 尾碼新增至電腦名稱稱的詳細資訊，請參閱 [CONFIGURE dns For Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)。