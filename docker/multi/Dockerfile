FROM ubuntu:bionic as multi1
LABEL maintainer="Igor Vincic <gorvin@users.noreply.github.com>"

RUN printf '#!/bin/bash\n\
echo hello multistage image 1\n'\
>> /first.sh \
&& chmod a+x /first.sh

CMD ["/first.sh"]

FROM ubuntu:bionic as multi2
LABEL maintainer="Igor Vincic <gorvin@users.noreply.github.com>"

RUN printf '#!/bin/bash\n\
echo hello multistage image 2\n'\
>> /second.sh \
&& chmod a+x /second.sh

CMD ["/second.sh"]

FROM ubuntu:bionic as final
LABEL maintainer="Igor Vincic <gorvin@users.noreply.github.com>"
COPY --from=multi1 /first.sh /first.sh
COPY --from=multi2 /second.sh /second.sh

RUN printf '#!/bin/bash\n\
/first.sh \n \
/second.sh \n' >> /final.sh \
&& chmod a+x /final.sh

CMD ["/final.sh"]
