# 1. Set a common base
FROM ubuntu:bionic as base

# 2. Set required CNB information
ENV CNB_USER_ID=1000
ENV CNB_GROUP_ID=1000
#@SUGGESTION
#CNB_STACK_ID="io.ballerina.samples.stacks.bionic"
ENV CNB_STACK_ID="io.buildpacks.choreo.stacks.bionic"
#@SUGGESTION
#CNB_STACK_ID="io.ballerina.samples.stacks.bionic"
LABEL io.buildpacks.stack.id="io.buildpacks.choreo.stacks.bionic"

# 3. Create the user
RUN groupadd cnb --gid ${CNB_GROUP_ID} && \
  useradd --uid ${CNB_USER_ID} --gid ${CNB_GROUP_ID} -m -s /bin/bash cnb

# ========== ADDED ===========
# 4. Install common packages
RUN apt-get update && \
  apt-get install -y xz-utils ca-certificates && \
  rm -rf /var/lib/apt/lists/*
