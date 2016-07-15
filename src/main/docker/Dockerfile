FROM soulwing/docker-wildfly10
COPY config.script ${project.build.finalName}.war /tmp/
RUN APPS_BASE=/apps && \
   $APPS_BASE/wildfly/bin/jboss-cli.sh --file=/tmp/config.script && \
   rm -fr /apps/wildfly/standalone/configuration/standalone_xml_history/ && \
   rm /tmp/config.script && \
   rm /tmp/${project.build.finalName}.war

CMD ["/apps/wildfly/bin/standalone.sh"]
